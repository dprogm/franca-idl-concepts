# Type Mappings

## Pimitive Types (Scalar Types)

| Franca IDL Type | Protocol Buffers Type | Protocol Buffers C++ Type | CommonAPI C++ Type |
| --- | --- | --- | --- |
| `UInt8` | `uint32` | `uint32_t` | `uint8_t` |
| `Int8` | `int32` | `int32_t` | `int8_t` |
| `UInt16` | `uint32` | `uint32_t` | `uint16_t` |
| `Int16` | `int32` | `int32_t` | `int16_t` |
| `UInt32` | `uint32` | `uint32_t` | `uint32_t` |
| `Int32` | `int32` | `int32_t` | `int32_t` |
| `UInt64` | `uint64` | `uint64_t` | `uint64_t` |
| `Int64` | `int64` | `int64_t` | `int64_t` |
| `Integer`<sup>[1]</sup> | - | - | - |
| `Boolean` | `bool` | `bool` | `bool` |
| `Float` | `float` | `float` | `float` |
| `Double` | `double` | `double` | `double` |
| `String` | `string` | `std::string` | `std::string` |
| `ByteBuffer` | `bytes` | `std::string` | `std::vector<uint8_t>` |

[1] This is currently not supported, but can be modeled by some basic integer type.

## Complex Types

| Franca IDL Type | Protocol Buffers Type | Protocol Buffers C++ Type | CommonAPI C++ Type |
| --- | --- | --- | --- |
| `array` | `repeated` | `Repeated[Ptr]Field`<sup>[1]</sup> | `std::vector<T>` |
| `enumeration` | `enum` | `enum`<sup>[2]</sup> | `CommonAPI::Enumeration` |
| `struct`<sup>[3]</sup> | `message` | `Message` | `CommonAPI::Struct` |
| `union` | `oneof` | `enum`<sup>[4]</sup> | `CommonAPI::Variant` |
| `map` | - | - | - |
| `typedef` | - | - | - |

[1] Concrete type depends on the contained type. \
[2] Provides additional functions for e.g. parsing and validation. \
[3] Inheritance will be mapped to a flat structure by simply combining the fields of the base and derived type. \
[4] Plus additional functions for accessing the concrete value.