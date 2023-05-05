# dartx
Extensions methods that adds functionality to Dart objects

This repository contains examples and explanations for using extension methods in Dart. Extension methods allow developers to add functionality to existing classes without modifying the original class.

## Getting Started

To use these examples, you will need to have Dart installed on your machine. You can download and install Dart from the official website [https://dart.dev/get-dart](https://dart.dev/get-dart), or you can quickly get started by using [dartpad](https://dartpad.dev/).

## Examples

The examples in this repository demonstrate how to use extension methods with different Dart classes. Each example is contained in its own file and includes comments explaining the code.

1. **[Null checker](#null-checker):** Extension methods on `Object?` that can return a boolean on a nullable object or carry out conditional operation.

### Null Checker

```dart
extension NullCheckerX on Object? {
  bool get isNull => this == null;

  bool get isNotNull => this != null;

  T ifNull<T>(
    T Function() followThrough, {
    required T Function() orElse,
  }) {
    if (this == null) {
      return followThrough();
    } else {
      return orElse();
    }
  }

  T ifNotNull<T>(
    T Function() followThrough, {
    required T Function() orElse,
  }) {
    if (this != null) {
      return followThrough();
    } else {
      return orElse();
    }
  }
}

// Usage
void main() {
  String? name = 'Peter Parker';

  name.ifNull<void>(
    () => print('I am No one'),
    orElse: () => print('I am $name'),
  ); // Output: 'I am Peter Parker'

  print('Is identity known: ${name.isNotNull}'); // Output: 'Is identity known: true'
}
```

## Contributing

If you have an example of how to use extension methods that you would like to contribute, please feel free to open a pull request. Contributions are always welcome.
