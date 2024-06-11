# LoopsOnOptionals

Mini library to extend optional chains to include for loops.

Example when using the [SwiftXML](https://github.com/stefanspringer1/SwiftXML) library:

With the `LoopsOnOptionals` package you can write:

```swift
extension XDocument {
   var metaDataSection: XElement? { ... }
}

for metaDataItem in myDocument.metaDataSection?.children("item") {
    ...
}
```

Of course, especially in this simple case you can express the same as follows, without using the `LoopsOnOptionals` package:

```swift
extension XDocument {
   var metaDataSection: XElement? { ... }
}

if let metaDataSection = myDocument.metaDataSection {
    for metaDataItem in metaDataSection.children("item") {
        ...
    }
}
```

But even more so in more complex situations, the introduction of such a `if let` (or `case let`) expression makes the code harder to understand.
