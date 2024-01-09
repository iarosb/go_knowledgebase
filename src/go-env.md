
# GOROOT -
           is a variable that defines where your Go SDK is located. You do not need to change this variable, unless you plan to use different Go versions.

# GOPATH -
          is a variable that defines the root of your workspace.
          By default = home directory.
          GOPATH stores your code base and all the files that are necessary for your development. You can use another directory as your workspace by configuring GOPATH for different scopes. GOPATH is the root of your workspace and contains the following folders:

    src/: location of Go source code (for example, .go, .c, .g, .s ).

    pkg/: location of compiled package code (for example, .a ).

    bin/: location of compiled executable programs built by Go.


You can configure GOPATH for the following scopes(is it a Goland-specific thing??):

    Global GOPATH: settings apply to all projects of a specific installation of GoLand.

    Project GOPATH: settings apply only to the current project.

    Module GOPATH: settings apply only to one module. A module can have an SDK that is different from those configured for a project. They can also carry a specific technology or a framework.

# GOBIN:
        Finally, $GOBIN defaults to the bin directory under $GOPATH, so you typically don't need to customize it either.

        As you noticed, you can use go env to check what Golang's notion of those variables are, if you leave them unset, in which case Golang should use the defaults described above.


# links:

  https://golang.org/cmd/go/#hdr-GOPATH_environment_variable

  https://www.jetbrains.com/help/go/configuring-goroot-and-gopath.html#configuring-gopath

  https://unix.stackexchange.com/questions/484660/how-to-properly-set-environment-variables-golang-on-manjaro
  

  https://golang.org/doc/tutorial/create-module   ---> more about modules and packages in a project

