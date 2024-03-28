# results

The `results` module contains functions that can extract and operate on a result's concrete type.

`is_success(r: result[any]) -> bool`

Checks if the supplied result is a `success`

`success(r: result[any]) -> any`

Extracts a result's`success` value

`is_failure(r: result[any]) -> bool`

Checks if the supplied result is an `error`

`failure(r: result[any]) -> error`

Extracts a result's `error` value