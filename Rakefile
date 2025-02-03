
require 'rake/clean'
require 'json'
require 'erb'

task :default => [:pdf]

#-----------------------------------------------------------------------------
# printable layer map diagrams
#-----------------------------------------------------------------------------

layers_pdf = 'all-layer-diagrams.pdf'
task :pdf => layers_pdf

layers_pdf_sequence = %w[
  base-layer-diagram-QWERTY
  alt-base-layer-diagram-qwerty
  cursor-layer-diagram
  number-layer-diagram
  function-layer-diagram
  symbol-layer-diagram
  mouse-layer-diagram
  system-layer-diagram
  emoji-layer-diagram
  world-layer-diagram
  lower-layer-diagram
  magic-layer-diagram
  factory-layer-diagram
  typing-layer-diagram
]

layer_pngs = Dir["layers/{#{layers_pdf_sequence.join(",")}}.png"]

layer_pdfs = layer_pngs.map do |png|
  pdf = png.ext('pdf')
  file pdf => png
  pdf
end
CLEAN.include layer_pdfs

file layers_pdf => layer_pdfs do |t|
  sh 'pdfunite', *t.prerequisites, t.name
end
CLOBBER.include layers_pdf

rule '.pdf' => '.png' do |t|
  sh 'gm', 'convert', t.source, t.name
end
