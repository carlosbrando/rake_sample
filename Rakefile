require "rake/clean"

CLEAN.include('*.o')
CLOBBER.include('sendmessage')

task :default => [:sendmessage]

SRC = FileList['*.c']
OBJ = SRC.ext('o')

rule '.o' => '.c' do |t|
  sh "gcc -c -o #{t.name} #{t.source}"
end

file "sendmessage" => OBJ do
  sh "gcc -o sendmessage #{OBJ}"
end

file "main.o" => ["main.c", "message.h"]
file "message.o" => ["message.c"]
