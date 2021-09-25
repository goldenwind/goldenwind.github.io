# PHP json_encode 函数详解

[TOCM]

[TOC]

## json_encode
(PHP 5 >= 5.2.0, PHP 7, PHP 8, PECL json >= 1.2.0)

**json_encode — 对变量进行 JSON 编码**

### 说明 ¶
```php
json_encode(mixed $value, int $options = 0, int $depth = 512): string|false
```

返回字符串，包含了 value 值 JSON 形式的表示。

编码受传入的 options 参数影响，此外浮点值的编码依赖于 serialize_precision。

### 参数 ¶
#### value
待编码的 value ，除了 资源(resource) 类型之外，可以为任何数据类型。

**所有字符串数据的编码必须是 UTF-8。**

**注意:**
PHP 实现了 JSON 的一个超集，参考 » RFC 7159.

#### options
由以下常量组成的二进制掩码： JSON_FORCE_OBJECT, JSON_HEX_QUOT, JSON_HEX_TAG, JSON_HEX_AMP, JSON_HEX_APOS, JSON_INVALID_UTF8_IGNORE, JSON_INVALID_UTF8_SUBSTITUTE, JSON_NUMERIC_CHECK, JSON_PARTIAL_OUTPUT_ON_ERROR, `JSON_PRESERVE_ZERO_FRACTION`, JSON_PRETTY_PRINT, JSON_UNESCAPED_LINE_TERMINATORS, JSON_UNESCAPED_SLASHES, JSON_UNESCAPED_UNICODE, `JSON_THROW_ON_ERROR`。 关于 JSON 常量详情参考 JSON 常量页面。

**depth**
设置最大深度。 必须大于0。

### 返回值 ¶
成功则返回 JSON 编码的 string 或者在失败时返回 false 。

更新日志 ¶
版本	说明
7.3.0	options 参数新增 JSON_THROW_ON_ERROR 常量。
7.2.0	options 参数新增 JSON_INVALID_UTF8_IGNORE 和 JSON_INVALID_UTF8_SUBSTITUTE 常量。
7.1.0	options 参数新增 JSON_UNESCAPED_LINE_TERMINATORS 常量。
7.1.0	对 Double 的值进行编码时，使用 serialize_precision 代替 precision。