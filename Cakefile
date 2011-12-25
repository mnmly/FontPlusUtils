{spawn, exec} = require 'child_process'

task 'doc', 'rebuild the Docco documentation', ->
  exec([
    'docco src/coffee/fontplus.utils.coffee'
    'sed "s/docco.css/http:\\/\\/jashkenas.github.com\\/docco\\/resources\\/docco.css/" < docs/fontplus.utils.html > index.html'
    'rm -r docs'
  ].join(' && '), (err) ->
    throw err if err
  )
