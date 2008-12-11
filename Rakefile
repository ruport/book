task :default => [:build]

task :build do
  sh "export PATH=/opt/local/bin:$PATH"
  sh "dblatex xml/book.xml -o book.pdf"
  sh "open book.pdf"
end

task :convert do
  basefile = File.basename(ARGV[1]).sub(/\.txt/,".xml")
  sh "export PATH=/opt/local/bin:$PATH"
  sh "asciidoc -d book -b docbook -o xml/ch_#{basefile} -s #{ARGV[1]}"
end
