---
layout: default
title: SQL Injection
nav: sql-injection
---

## SQL Injection

SQL injection is an attack involving a web facing input on a website or other application, a SQL command is input into the input in a way which allows it to byass the client and server levels making its way to the database level.

### Preventing SQL Injection

SQL injection being an old attack is relatively easy to prevent. It simply requires a step called "sanatization" in which any speciale charachters are escaped, thus preventing them from activating any type of command at the SQL level.

An example of sanatizing a string in PHP:

    $firstname = mysqli_real_escape_string($con, $_POST['firstname']);

In other cases a library might automatically provide sanatization witout the developer ever having to think about it, for example `node-mysql` a node.js library for working with MySQL.

Yet it is important to consider as even today when building on some use case specific technology, say an IoT device with a MySQL database on device, one might forget to perform the sanatization step and create a security vulnerability.

## Example Queries on Vulnerable Sites

Say you find a website which has a URL in the format below:

    website.com/index.php?id=1234

Notice that after the `?` there is an `id=1234`, this identifies the user to fetch.

In a website vulnerable to injection you may be able to do something like:

    website.com/index.php?id=1234 AND id=2222

Doing could potentially return the logged in user and another user with ID of 2222.

If we could find *(or guess)* the name of the SQL table holding passwords something like this could be done:

    website.com/index.php?id=1234 union select password from user;


### Shell Shock

Another attack which existed for a brief time that was similar to SQL injection was call shell shock.

Shell Shock allowed a command which normally be limited by permissions by inserting the code into an environment variable, similar to an SQL Injection.

    curl -H "user-agent: () { :; }; echo; echo; /bin/bash -c 'cat /etc/passwd'" \
    http://localhost:8080/cgi-bin/vulnerable

Shell Shock has been patched on all modern unix operating systems, however the exploit having been present from 1989 to 2014 may still be present on several older machines and servers which have not been updated.
