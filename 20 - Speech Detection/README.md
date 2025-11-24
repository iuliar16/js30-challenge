# PROJECT DESCRIPTION

This project is a live speech-to-text notepad in the browser.

We use a web speech API (const recognition = new SpeechRecognition())

interimResults = true means we will see partial (non-final) hypotheses update live as we speak, not just the final result

We use document.createElement("p") to create the first paragraph where the transcription will appear.

We ass an event listener to recognition (result event) that fires whenever the engine has new text.
e.results in an array of result objects. Each has alternatives by confidence (result[0] is the best guess).

We map to the top alternative’s .transcript, then join("") because you may receive multiple segments in one event.

const poopScript = transcript.replace(/poop|poo|shit|dump/gi, "💩");
p.textContent = poopScript;

This is a reges to replace the words poop, poo, etc with an emoji.

isFinal flag shows the segment is finalized and we havw to start a new paragraph.

recognition.addEventListener("end", recognition.start);
recognition.start();
These line should make sure that on end, we call start again to loop, but to me this did not work, after I took a break of speaking the listening did not seem to start again.

# WHAT I LEARNED

I learned how to use the web speech api and how to create that effect of typying as you speak using the result event.
