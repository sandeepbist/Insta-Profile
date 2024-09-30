<script>
  export let posts;
</script>

<div class="posts">
  {#each posts as post}
    <div class="post">
      <img src={post.node.display_url} alt="" />
    </div>
  {/each}
</div>

<style>
  .posts {
    margin-top: 10px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
  .posts .post {
    width: 48%;
  }
  .posts .post img {
    width: 100%;
    height: 220px;
    object-fit: cover;
  }
</style>
