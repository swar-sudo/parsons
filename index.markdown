---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

## Parsons 1: Film
Crea una cartella chiamata "film" e "film2"
In "film" crea i file avventura.txt, azione.txt e fantascienza.txt
Sposta tutti i file da film a film2
Elimina la cartella "film"
Mostra la lista dettagliata di file e directory

<div id="p1-sortableTrash" class="sortable-code"></div>
<div id="p1-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p1-feedbackLink" value="Get Feedback" type="button" />
    <input id="p1-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript"> 
(function(){
  var initial = "mkdir film
\n" +
    "mkdir film2
\n" +
    "cd film
\n" +
    "touch avventura.txt azione.txt fantascienza.txt
\n" +
    "cd ..
\n" +
    "mv film/*.txt film2/
\n" +
    "rmdir film
\n" +
    "ls -la film2/
\n" +
    "ls -la
\n" +
    "rmdir canzoni
\n" +
    "#distractor
\n" +
    "mkdir canzoni#distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p1-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p1-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>
