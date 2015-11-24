## lh-cpp Snippets, templates and wizards

### Contents

  * [Remarks](#remarks)
  * [Control Statements](#control-statements)
      * [cpp/catch](#cppcatch)
      * [cpp/for-enum](#cppfor-enum)
      * [cpp/for-iterator](#cppfor-iterator)
      * [cpp/for-range](#cppfor-range)
      * [cpp/fori](#cppfori)
      * [cpp/foriN](#cppforin)
      * [cpp/namespace](#cppnamespace)
      * [cpp/throw](#cppthrow)
      * [cpp/try](#cpptry)
      * [cpp/while-getline](#cppwhile-getline)
  * [Standard (and boost) Types](#standard-and-boost-types)
      * [cpp/auto_ptr](#cppauto_ptr)
      * [cpp/auto_ptr-instance](#cppauto_ptr-instance)
      * [cpp/file](#cppfile)
      * [cpp/list](#cpplist)
      * [cpp/map](#cppmap)
      * [cpp/noncopyable](#cppnoncopyable)
      * [cpp/path](#cpppath)
      * [cpp/ptr_vector](#cppptr_vector)
      * [cpp/set](#cppset)
      * [cpp/shared_ptr](#cppshared_ptr)
      * [cpp/string](#cppstring)
      * [cpp/unique_ptr](#cppunique_ptr)
      * [cpp/vector](#cppvector)
      * [cpp/weak_ptr](#cppweak_ptr)
  * [Standard (and boost) Functions and Idioms](#standard-and-boost-functions-and-idioms)
      * [c/assert](#cassert)
      * [c/rand_init](#crand_init)
      * [c/realloc](#crealloc)
      * [cpp/array_size](#cpparray_size)
      * [cpp/b-e](#cppb-e)
      * [cpp/cerr](#cppcerr)
      * [cpp/cin](#cppcin)
      * [cpp/copy](#cppcopy)
      * [cpp/cout](#cppcout)
      * [cpp/ends_with](#cppends_with)
      * [cpp/erase-remove](#cpperase-remove)
      * [cpp/iss](#cppiss)
      * [cpp/oss](#cpposs)
      * [cpp/sort](#cppsort)
      * [cpp/starts_with](#cppstarts_with)
      * [cpp/static_assert](#cppstatic_assert)
  * [Classes](#classes)
    * [Class Elements](#class-elements)
      * [cpp/assignment-operator](#cppassignment-operator)
      * [cpp/bool-operator](#cppbool-operator)
      * [cpp/copy-and-swap](#cppcopy-and-swap)
      * [cpp/copy-back_inserter](#cppcopy-back_inserter)
      * [cpp/copy-constructor](#cppcopy-constructor)
      * [cpp/default-constructor](#cppdefault-constructor)
      * [cpp/destructor](#cppdestructor)
      * [cpp/operator-binary](#cppoperator-binary)
      * [cpp/stream-extractor](#cppstream-extractor)
      * [cpp/stream-inserter](#cppstream-inserter)
    * [Class Patterns](#class-patterns)
      * [cpp/abs-rel](#cppabs-rel)
      * [cpp/class](#cppclass)
      * [cpp/enum](#cppenum)
      * [cpp/enum2](#cppenum2)
      * [cpp/enum2-impl](#cppenum2-impl)
      * [cpp/singleton](#cppsingleton)
      * [cpp/traits](#cpptraits)
  * [Doxygen](#doxygen)
      * [dox/author](#doxauthor)
      * [dox/code](#doxcode)
      * [dox/em](#doxem)
      * [dox/file](#doxfile)
      * [dox/function](#doxfunction)
      * [dox/group](#doxgroup)
      * [dox/html](#doxhtml)
      * [dox/ingroup](#doxingroup)
      * [dox/since](#doxsince)
      * [dox/tt](#doxtt)
  * [Miscelleanous](#miscelleanous)
      * [cpp/benchmark](#cppbenchmark)
      * [cpp/otb-sug-latex](#cppotb-sug-latex)
      * [cpp/otb-sug-snippet](#cppotb-sug-snippet)
      * [cpp/utf8](#cpputf8)
  * [Internal templates](#internal-templates)
      * [cpp/internals/abs-rel-shared](#cppinternalsabs-rel-shared)
      * [cpp/internals/formatted-comment](#cppinternalsformatted-comment)
      * [cpp/internals/function-comment](#cppinternalsfunction-comment)
      * [cpp/internals/stream-common](#cppinternalsstream-common)
      * [cpp/internals/stream-implementation](#cppinternalsstream-implementation)
      * [cpp/internals/stream-signature](#cppinternalsstream-signature)

### Remarks

 * Styling options from
   [lh-dev](http://github.com/LucHermitte/lh-dev#options-1) are applied on the
   snippets. In other words, the code presented here may be formatted
   differently regarding spaces and newlines.

 * [Placeholders](http://github.com/LucHermitte/lh-brackets) are represented
   within «French quotation marks».

### Control Statements
##### cpp/catch
**Produces:**
```C++
catch(«...») {
    «catch-code»
}
```

**Surround:**
  1. The selection can be surrounded to become the catch-code

##### cpp/for-enum
**Produces:**
```C++
for («Enum»::type «exception_type»(«exception_args»)=«Enum»::type()
   ; «exception_type»(«exception_args»)!=«Enum»::MAX__
   ; ++«exception_type»(«exception_args»))
{
    «code»
}
```

**Surround:**
  1. The selection can be surrounded to become the loop code

**Note:**
  *  This snippet is meant to be used with [cpp/enum](#cppenum) snippets

##### cpp/for-iterator
**Produces:**
```C++
for («T»::«const_»iterator «b»=«code».begin(), «exception_type»(«exception_args»)=«code».end()
    ; «b»!=«exception_type»(«exception_args»)
    ; ++«b»)
{
    «code»
}
```

**Surround:**
  1. The selection can be surrounded to become the loop code

**Notes:**
  *  Container name («code»), and iterators names («b» and «exception_type»(«exception_args»)) are asked to the end user

##### cpp/for-range
**Produces:**
```C++
for («type» «elem» : «range») {
    «code»
}
```

**Parameters:**
  * _type_, default: `auto&&`
  * _elem_, default: `e`
  * _range_, default: `«range»`

**Surround:**
  1. The selection can be surrounded to become the loop code

##### cpp/fori
**Produces:**
```C++
for («int» «i»=0;«i»!=«N»;++«i») {
    «code»
}
```

**Surround:**
  1. The selection can be surrounded to become the loop code

##### cpp/foriN
**Produces:**
```C++
for («std::size_t» «i»=0, «N»=...;«i»!=«N»;++«i») {
    «code»
}
```

**Surround:**
  1. The selection can be surrounded to become the loop code

##### cpp/namespace
**Produces:** `namespace «ns» { ... } // «ns»`

**Parameters:**
  * _ns_, default: `(bg):[{ft}_]project_namespace`

**Options:**
  * [`(bg):[{ft}_]project_namespace`](options.md#bgft_project_namespace), which
    defaults to `«ns»`
  * [`lh#cpp#use_cpp17()`](options.md#bgcpp_std_flavour)
  * [`(bg):cpp_use_nested_namespaces`](options.md#bgcpp_use_nested_namespaces)

**Surround:**
  1. The selection can be surrounded to become the namespace code

**Notes:**
  * If the namespace parameter is `foo::bar`, this snippet produces two nested
    namespace definitions.
  * If C++17 flavour is selected, and `(bg):cpp_use_nested_namespaces` is true,
    then C++17 a _nested namespace_ will be used.

##### cpp/throw
**Produces:**
  * `throw «exception_type»(«exception_args»);` (within code context)
  * or `@throw` (within Doxygen comments)«»

**Parameters:**
  * `exception_text`, default: «text»

**Options:**
  * `(bg):({ft}_)exception_type`, default: `std:runtime_error`
  * `(bg):({ft}_)exception_args`, default: `v:1_`, functor that gets `exception_txt` injected as parameter

**Also includes:**
  * `<stdexcept>` if `exception_type` starts with `std::`

**Variation Points:**
  * 'throw', 'cpp', '"Cannot decode'.s:enum_name.'"'

##### cpp/try
**Produces:**
```C++
try {
    «code»
} catch(«std::exception const& e») {
    «catch-code»
}
```

**Surround:**
  1. The selection can be surrounded to become the try-code
  2. The selection can be surrounded to become the catch-code

##### cpp/while-getline
**Produces:**
```C++
while(std::getline(«stream»,«line»)) {
    «code»;
}
```

**Surround:**
  1. The selection can be surrounded to become the loop code

**Also includes:**
  * `<string>`


### Standard (and boost) Types
##### cpp/auto_ptr
**Produces:** `std::auto_ptr<«type»>`

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * `<memory>`

##### cpp/auto_ptr-instance
**Produces:** `std::auto_ptr<«type»> ptr(new «type»(args));`

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * `<memory>`

**Notes:**
  * I hesitate to called it `cpp/make_auto_ptr`

##### cpp/file
**Produces:** `«i»fstream f(«filename»);`

**Surround:**
  1. The selection can be surrounded to become the filename

**Also includes:**
  * `<fstream>`

##### cpp/list
**Produces:** `std::list<«type»> «»`

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * `<list>`

##### cpp/map
**Produces:** `std::map<«key»,«value»> «»`

**Surround:**
  1. The selection can be surrounded to become the value type
  2. The selection can be surrounded to become the key type

**Also includes:**
  * `<map>`

##### cpp/noncopyable
**Produces:** `boost::noncopyable`

**Also includes:**
  * `<boost/noncopyable.hpp>`

##### cpp/path
**Produces:** `boost::filesystem::path`

**Also includes:**
  * `<boost/filesystem.hpp>`

##### cpp/ptr_vector
**Produces:** `boost::ptr_vector<«type»> «»`

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * lh#dev#import#add("<boost/ptr_container/ptr_vector.hpp>")

##### cpp/set
**Produces:** `std::set<«type»> «»`

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * <set>

##### cpp/shared_ptr
**Produces:**
  * `std::shared_ptr<«type»> «»`, in [C++11 or more](options.md#bgcpp_std_flavour)
  * `boost::shared_ptr<«type»> «»`, otherwise

**Options:**
  * [`lh#cpp#use_cpp11()`](options.md#bgcpp_std_flavour)

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * `<memory>` in C++11
  * `<boost/shared_ptr.hpp>` otherwise

##### cpp/string
**Produces:** `std::string «»`

**Also includes:**
  * `<string>`

##### cpp/unique_ptr
**Produces:** `std::unique_ptr<«type»>`

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * `<memory>`

##### cpp/vector
**Produces:** `std::vector<«type»> «»`

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * `<vector>`

##### cpp/weak_ptr
**Produces:**
  * `std::weak_ptr<«type»> «»`, in [C++11 or more](options.md#bgcpp_std_flavour)
  * `boost::weak_ptr<«type»> «»`, otherwise

**Options:**
  * [`lh#cpp#use_cpp11()`](options.md#bgcpp_std_flavour)

**Surround:**
  1. The selection can be surrounded to become the value type

**Also includes:**
  * `<memory>` in C++11
  * `<boost/shared_ptr.hpp>` otherwise


### Standard (and boost) Functions and Idioms
##### c/assert
**Produces:** `assert(«assertion»)`

**Surround:**
  1. The selection can be surrounded to become the «assertion»

**Also includes:**
  * `<assert.h>`

##### c/rand_init
**Produces:** `srand(time(NULL));`

**Also includes:**
  * `<time.h>` in C, `<ctime>` in C++
  * `<stdlib.h>` in C, `<cstdlib>` in C++

##### c/realloc
**Produces:**
```C++
type lhs = (type) realloc(ptr, size); macro
if (! lhs) {                          macro
    free(ptr);                        macro
    ptr = NULL;                       macro
    count = 0;                        macro
    «error_message»;                  macro
    return false                      macro
}                                     macro
ptr = lhs;
```

**Parameters:**
  * A dictionary that contains:
    * `"ptr"`, default `«p»`
    * `"lhs"`, default `new ` + _ptr_
    * `"type"`, default `«T»`
    * `"count"`, default `«count»`
    * `"size"`, default _count_ `* sizeof(`_type_`)`
    * `"realloc"`, default `realloc`
    * `"free"`, default `free`
    * `"false"`, default `false`
    * `"macro"`, default: an empty string, expected value: `\\`

##### cpp/array_size
**Produces:**
```C++
// C++98/03
array_size(«array»)
// C++11
std::extent<decltype(«array»)>::value`
// C++17
std::size(«array»)
```

**Parameters:**
  * _array_, default «array»

**Options:**
  * [`lh#cpp#use_cpp11()` and `lh#cpp#use_cpp17()`](options.md#bgcpp_std_flavour)

**Surround:**
  1. The selection can be surrounded to become the array name

**Also includes:**
  * `<type_traits>` in C++11

**Notes:**
  * In C++98/03, the definition of `array_size()` macro is provided along the
    way

**TODO:**
  * Make the snippet easier to use multiple times in C++98/03
  * Define the unsafe C equivalent `c/array_size`:
    `sizeof «array»/sizeof «array»[0]`

##### cpp/b-e
**Produces:**
  * or `std::begin(«container»), std::end(«container»)`
    if [C++11 flavour](options.md#bgcpp_std_flavour) is used, or
    if [`(bg):({ft}_)begin_end_style`](options.md#bgft_begin_end_style) equals
    "std"
  * or `boost::begin(«container»), boost::end(«container»)`
    if [`(bg):({ft}_)begin_end_style`](options.md#bgft_begin_end_style) equals
    "boost"
  * or `begin(«container»), end(«container»)`
  * or `«container».begin(), «container».end()`
    if [`(bg):({ft}_)begin_end_style`](options.md#bgft_begin_end_style) equals
    "adl"

**Parameters:**
  * _container_, default: «container»

**Options:**
  * [C++11 flavour](options.md#bgcpp_std_flavour)
  * [`(bg):({ft}_)begin_end_style`](options.md#bgft_begin_end_style)

**TODO:**
  * Surround container

##### cpp/cerr
**Produces:** `std::cerr <<`

**Also includes:**
  * `<iostream>`

##### cpp/cin
**Produces:** `std::cin >>`

**Also includes:**
  * `<iostream>`

##### cpp/copy
**Produces:** `std::copy(first, last, dest)`

**Parameters:**
  * _container_, default: «container»

**Surround:**
  1. The selection can be surrounded to become the container name

**Also includes:**
  * `<algorithm>`

**TODO:**
  * Use `cpp/b-e` snippet

##### cpp/cout
**Produces:** `std::cout <<`

**Also includes:**
  * `<iostream>`

##### cpp/ends_with
**Produces:** `boost::algorithm::ends_with(«input», «prefix_searched»)`

**Also includes:**
  * `<boost/algorithm/string/predicate.hpp>`

##### cpp/erase-remove
**Produces:** `erase-remove idiom`

**Parameters:**
  * _container_, default: «container»

**Surround:**
  1. The selection can be surrounded to become the container name

**Also includes:**
  * `<algorithm>`

**TODO:**
  * Use `cpp/b-e` snippet

##### cpp/iss
**Produces:**
```C++
std::istringstream iss(str);
if (iss >> «»)
{ ... }
```

**Also includes:**
  * `<sstream>`

##### cpp/oss
**Produces:**
```C++
std::ostringstream oss(str);
oss << «»;
```

**Also includes:**
  * `<sstream>`

##### cpp/sort
**Produces:** `std::sort(range.begin(), range.end());`

**Parameters:**
  * _range_, default: «range»

**Surround:**
  1. The selection can be surrounded to become the range name

**Also includes:**
  * `<algorithm>`

**TODO:**
  * Use `cpp/b-e` snippet

##### cpp/starts_with
**Produces:** `boost::algorithm::starts_with(«input», «prefix_searched»)`

**Also includes:**
  * `<boost/algorithm/string/predicate.hpp>`

##### cpp/static_assert
**Produces:**
```C++
// C++11
static_assert(cond, msg)
// C++98/03
BOOST_STATIC_ASSERT(cond)
```

**Parameters:**
  *  _condition_, default: «condition»
  *  _message_, default: «message»

**Options:**
  * [C++11 flavour](options.md#bgcpp_std_flavour)

**Also includes:**
  * `<boost/static_assert.hpp>`, in C++98/03

### Classes

#### Class Elements
##### cpp/assignment-operator
##### cpp/bool-operator
##### cpp/copy-and-swap
##### cpp/copy-back_inserter
##### cpp/copy-constructor
##### cpp/default-constructor
##### cpp/destructor
##### cpp/operator-binary
##### cpp/stream-extractor
##### cpp/stream-inserter

#### Class Patterns
##### cpp/abs-rel
##### cpp/class
##### cpp/enum
##### cpp/enum2
##### cpp/enum2-impl
##### cpp/singleton
##### cpp/traits

### Doxygen
##### dox/author
##### dox/code
##### dox/em
##### dox/file
##### dox/function
##### dox/group
##### dox/html
##### dox/ingroup
##### dox/since
##### dox/tt

### Miscelleanous
##### cpp/benchmark
##### cpp/otb-sug-latex
##### cpp/otb-sug-snippet
##### cpp/utf8

### Internal templates
##### cpp/internals/abs-rel-shared
##### cpp/internals/formatted-comment
##### cpp/internals/function-comment
##### cpp/internals/stream-common
##### cpp/internals/stream-implementation
##### cpp/internals/stream-signature