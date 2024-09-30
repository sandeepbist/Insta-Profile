<script>
  export let user;
</script>

<div class="profile">
  <div class="avatar">
    <img src={user.profile_pic_url_hd} alt="Profile Photo" />
  </div>
  <div class="info">
    <h2>
      {user.full_name}
    </h2>
    <p>
      {user.biography}
    </p>
    <div class="counts">
      <div>
        <div>Followers</div>
        <div>
          {user.edge_followed_by.count}
        </div>
      </div>
      <div>
        <div>Following</div>
        <div>
          {user.edge_follow.count}
        </div>
      </div>
      <div>
        <div>Posts</div>
        <div>
          {user.edge_owner_to_timeline_media.count}
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  .profile {
    padding: 20px 50px;
    background: #eee;
    display: flex;
  }
  .profile * {
    margin: 0px;
  }
  .profile .avatar {
    width: 150px;
    text-align: center;
  }
  .profile .avatar img {
    width: 120px;
    border-radius: 50%;
  }
  .profile .info {
    flex: 1;
    padding-left: 10px;
  }
  .profile .info p {
    margin: 10px 0px;
  }
  .profile .info .counts {
    display: flex;
  }
  .profile .info .counts > div {
    width: 33.33%;
  }
</style>
