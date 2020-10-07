# Zbar

Scan one or more barcodes from a JPEG image.

The API for this library is very simple:

```elixir
iex> File.read!("file_dir.jpg") |> Zbar.scan("colorspace_name")
%Zbar.Symbol{
  data: "REF1",
  points: [{40, 40}, {40, 250}, {250, 250}, {250, 40}],
  quality: 1,
  type: "QR-Code"
}
```
Default colorspace is "color". Change to "gray" to enable scanning images in grayscale.

More detailed API documentation can be found at
[https://hexdocs.pm/zbar](https://hexdocs.pm/zbar).

## Installation

This package is [available in Hex](https://hex.pm/packages/zbar) and can be
installed by adding `:zbar` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [{:zbar, "~> 0.2", github: "Fastcomm/zbar"}]
end
```

You will also need to have `zbar` and `libjpeg` installed in order to compile
the required native code. On OSX with Homebrew, this is as simple as:

```bash
$ brew install zbar libjpeg
```
