# frozen_string_literal: true

directory "vendor"

task harmony: :vendor do
  require "net/http"

  base_uri = URI("https://raw.githubusercontent.com/evilmartians/harmony/refs/heads/main/")

  ["source.json", "LICENSE"].each do |filename|
    content = Net::HTTP.get(base_uri + filename)

    File.write("vendor/#{filename}", content)
  end
end

task :evil do
  require "json"
  require "psych"

  harmony = JSON.parse(File.read("vendor/source.json"))

  harmonic_evil = {
    "scheme" => "Harmonic Evil",
    "author" => "skipkayhil",
    "base00" => harmony["Slate/900"]["$srgbFallback"][1..],
    "base01" => harmony["Slate/800"]["$srgbFallback"][1..],
    "base02" => harmony["Slate/700"]["$srgbFallback"][1..],
    "base03" => harmony["Slate/600"]["$srgbFallback"][1..],
    "base04" => harmony["Slate/400"]["$srgbFallback"][1..],
    "base05" => harmony["Slate/300"]["$srgbFallback"][1..],
    "base06" => harmony["Slate/200"]["$srgbFallback"][1..],
    "base07" => harmony["Slate/100"]["$srgbFallback"][1..],
    "base08" => harmony["Red/500"]["$srgbFallback"][1..],
    "base09" => harmony["Orange/400"]["$srgbFallback"][1..],
    "base0A" => harmony["Yellow/300"]["$srgbFallback"][1..],
    "base0B" => harmony["Green/400"]["$srgbFallback"][1..],
    "base0C" => harmony["Cyan/300"]["$srgbFallback"][1..],
    "base0D" => harmony["Blue/300"]["$srgbFallback"][1..],
    "base0E" => harmony["Violet/400"]["$srgbFallback"][1..],
    "base0F" => harmony["Pink/400"]["$srgbFallback"][1..],
  }

  File.write("harmonic-evil.yaml", Psych.dump(harmonic_evil))
end

task default: :evil
