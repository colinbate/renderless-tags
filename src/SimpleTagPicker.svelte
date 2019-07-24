<script>
import RenderlessTagPicker from './RenderlessTagPicker.svelte';
export let tags;
</script>
<style>
.tags-input {
  border: 1px solid hsl(210, 5%, 80%);
  padding: 0.5rem 0.5rem 0 0.5rem;
  border-radius: 0.25rem;
  display: flex;
  align-items: center;
  align-content: space-between;
  flex-wrap: wrap;
  max-width: 34rem;
}
.tag {
  background-color: hsl(210, 80%, 90%);
  border-radius: 0.25rem;
  padding: 0.25rem;
  margin: 0 0.5rem 0.5rem 0;
  line-height: 1;
  display: inline-flex;
  align-items: center;
}
.remove {
  border: 0;
  cursor: pointer;
  background-color: transparent;
  padding: 0.2rem 0.2rem 0.4rem 0.2rem;
  display: inline-block;
  margin: 0;
  margin-left: 0.25rem;
  line-height: 1;
  color: #2779bd;
  font-size: 1.125rem;
}
.tag-input {
  margin: 0 0 0.5rem 0;
  flex-grow: 1;
}
</style>
<RenderlessTagPicker bind:tags let:addTag let:removeTag let:newTag let:handleInput let:handleKeys>
	<div class="tags-input">
  {#each tags as tag}
    <span class="tag"><span>{tag}</span><button type="button" class="remove" on:click={() => removeTag(tag)}>&times;</button></span>
  {/each}
    <input type="text" class="tag-input" placeholder="Add tag..." value={newTag} on:input={handleInput} on:keydown={handleKeys}>
  </div>
</RenderlessTagPicker>