---
sidebar_position: 5
---

# zconst

`zconst` is a helper package that provides constants for common use cases such as error codes, Zog Types and more. Every constant here is just a string so using `zconst` is completely optional. This is the entire code of the zconst package as of version 0.11.0:

```go

const (
	ZogTag = "zog"
)

// Map used to format errors in Zog. Both ZogType & ZogErrCode are just strings
type LangMap = map[ZogType]map[ZogErrCode]string

type ZogType = string

const (
	TypeString ZogType = "string"
	TypeNumber ZogType = "number"
	TypeBool   ZogType = "bool"
	TypeTime   ZogType = "time"
	TypeSlice  ZogType = "slice"
	TypeStruct ZogType = "struct"
)

type ZogErrCode = string

const (
	ErrCodeCustom   ZogErrCode = "custom"   // all
	ErrCodeRequired ZogErrCode = "required" // all
	ErrCodeNotNil   ZogErrCode = "not_nil"  // all (technically only applies to pointers)
	ErrCodeCoerce   ZogErrCode = "coerce"   // all
	// all. Applied when other errror code is not implemented. Required to be implemented for every zog type!
	ErrCodeFallback ZogErrCode = "fallback"
	ErrCodeEQ       ZogErrCode = "eq"             // number, time, string
	ErrCodeOneOf    ZogErrCode = "one_of_options" // string or number

	ErrCodeMin      ZogErrCode = "min"       // string, slice
	ErrCodeMax      ZogErrCode = "max"       // string, slice
	ErrCodeLen      ZogErrCode = "len"       // string, slice
	ErrCodeContains ZogErrCode = "contained" // string, slice

	// number only
	ErrCodeLTE ZogErrCode = "lte" // number
	ErrCodeLT  ZogErrCode = "lt"  // number
	ErrCodeGTE ZogErrCode = "gte" // number
	ErrCodeGT  ZogErrCode = "gt"  // number

	// string only
	ErrCodeEmail           ZogErrCode = "email"
	ErrCodeUUID            ZogErrCode = "uuid"
	ErrCodeMatch           ZogErrCode = "match"
	ErrCodeURL             ZogErrCode = "url"
	ErrCodeHasPrefix       ZogErrCode = "prefix"
	ErrCodeHasSuffix       ZogErrCode = "suffix"
	ErrCodeContainsUpper   ZogErrCode = "contains_upper"
	ErrCodeContainsLower   ZogErrCode = "contains_lower"
	ErrCodeContainsDigit   ZogErrCode = "contains_digit"
	ErrCodeContainsSpecial ZogErrCode = "contains_special"
	// time only
	ErrCodeAfter  ZogErrCode = "after"
	ErrCodeBefore ZogErrCode = "before"
	// bool only
	ErrCodeTrue  ZogErrCode = "true"
	ErrCodeFalse ZogErrCode = "false"

	// ZHTTP ERRORS
	ErrCodeZHTTPInvalidJSON  ZogErrCode = "invalid_json"  // invalid json body
	ErrCodeZHTTPInvalidForm  ZogErrCode = "invalid_form"  // invalid form data
	ErrCodeZHTTPInvalidQuery ZogErrCode = "invalid_query" // invalid query params
)
```
