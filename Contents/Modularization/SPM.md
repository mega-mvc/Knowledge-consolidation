# Package.swift
## Products
A target may build either a library or an executable as its product. A library contains a module that can be imported by other Swift code. An executable is a program that can be run by the operating system.

A package product defines an externally visible build artifact that's available to clients of a package. The product is assembled from the build artifacts of one or more of the package's targets.

## Target
A target, the basic building block of a Swift package.

Each target contains a set of source files that are compiled into a module or test suite. You can vend targets to other packages by defining products that include the targets.

## Resource
Similar to source code, the Swift Package Manager scopes resources to a target, so you must put them into the folder that corresponds to the target they belong to. **For example, any resources for the MyLibrary target must reside in Sources/MyLibrary.**

Use subdirectories to organize your resource files in a way that simplifies file identification and management. For example, put all resource files into a directory named Resources, so they reside at Sources/MyLibrary/Resources.

## Version-specific Tag Selection
We can use swift version tag to determine the last supported swift version of a package version. Example: 
package Foo has the tags [1.0.0, 1.2.0@swift-3, 1.3.0]. If version 3.0 of the package manager is evaluating the available versions for this repository, it will only ever consider version 1.2.0. However, version 4.0 would consider only 1.0.0 and 1.3.0.

## Version-specific Manifest Selection
We can use tag in package manifest name to support multiple Swift Package tool version. e.g: 
`Package.swift` (tools version 3.0) `Package@swift-4.swift` (tools version 4.0) `Package@swift-4.2.swift` (tools version 4.2)

The package manager will pick `Package.swift` on Swift 3, `Package@swift-4.swift` on Swift 4, and `Package@swift-4.2.swift` on Swift 4.2 and above because its tools version will be most compatible with future version of the package manager.

# Resolving Versions (Package.resolved File)
For a Package itself, the `Package.resolved` is located at the top level of the package source.

For a Project, the `Package.resolved` is located inside **.xcodeproj/.xcworkspace/xcshareddata/swiftpm**

# Plugins



