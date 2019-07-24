<script>
export let tags = [];
let newTag = '';

function addTag() {
  if (!newTag.trim().length || tags.includes(newTag.trim())) {
    return;
  }
  tags = [...tags, newTag.trim()];
  newTag = '';
}

function removeTag(tag) {
  console.log('Removing tag:', tag);
  tags = tags.filter(t => t !== tag);
}

function handleInput(ev) {
  newTag = ev.target.value;
}

function handleKeys(ev) {
  if (ev.keyCode === 13) {
    ev.preventDefault();
    addTag();
  }
}
</script>
<slot {addTag} {removeTag} {newTag} {handleInput} {handleKeys}></slot>