# :question: FAQ

A list of frequently asked questions

## :wrench: Virtual Environments

Python virtual environments are a powerful tool that can help you manage dependencies and isolate your projects from one another. Here are some benefits of using virtual environments in Python:

1. **Avoid system pollution**: Virtual environments allow you to install packages and dependencies without affecting the system's global Python installation. This helps you avoid conflicts between different versions of packages and dependencies.

2. **Sidestep dependency conflicts**: Virtual environments allow you to create isolated environments for each project, which means that you can have different versions of the same package installed in different environments without any conflicts.

3. **Minimize reproducibility issues**: Virtual environments help you ensure that your code runs consistently across different machines and platforms. By creating an environment with the same dependencies as your project, you can ensure that your code will run the same way on different machines.

4. **Dodge installation privilege lockouts**: Virtual environments allow you to install packages and dependencies without requiring administrator privileges. This can be especially useful if you're working on a shared machine or don't have administrator access.

5. **Enhanced collaboration**: Virtual environments can help you collaborate with other developers more effectively. By sharing your virtual environment configuration files, you can ensure that everyone is using the same dependencies and versions of packages.

To use virtual environments in Python, you can use the built-in `venv` module or third-party tools like `virtualenv` or `conda`. You can create a new virtual environment for your project, activate it, and install packages into it. Once you're done working on your project, you can deactivate the environment and switch to a different one.

### requirements.txt

A `requirements.txt` file is a plain text file that lists the packages and libraries required for a Python project. It is used to specify the exact versions of these packages and libraries, making it easier to install, review, and reproduce the requirements of an environment. This file is usually stored in the root directory of the project and can be used to download all the packages at once with a pip command.

For instance, if you have a Python project that uses a specific version of a package, you can list that package and its version in the requirements.txt file. When you share your project with others, they can install the same Python modules you have listed in your requirements file and run your project without any problems.

To create a `requirements.txt` file, you can navigate to your Python project directory and create a new .txt document named `requirements.txt`. Then, add the names of the modules you would like to install, along with the required version, on separate lines. You can also generate a `requirements.txt` file directly from the command line with the following command:

`pip freeze > requirements.txt`

### Manual

```
python -m venv .venv
.venv\Scripts\activate
python -m pip install -U pip
pip install -r requirements.txt
```

### Use VS Code

## :interrobang: SSL Error when using [`fetch_openml`](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_openml.html)

Add the following two lines of code at the top of the Python script.

> See [reference](https://stackoverflow.com/a/69120255) from StackOverflow.

```py linenums="1"
import ssl
ssl._create_default_https_context = ssl._create_unverified_context
```

The first line imports the `ssl` module, which provides access to Transport Layer Security (TLS) and Secure Sockets Layer (SSL) cryptographic protocols. The second line sets the default SSL context to an unverified context. This is useful when you want to **bypass SSL certificate verification** for testing or development purposes.

By default, Python's SSL context verifies the server's SSL certificate to ensure that the connection is secure. However, in some cases, such as when working with self-signed certificates or testing with a local server, you may want to disable certificate verification. This is where the `ssl._create_unverified_context()` method comes in handy. It creates an SSL context that does not verify the server's SSL certificate, allowing you to establish a connection even if the certificate is invalid or self-signed.
