# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
<% @post_images.each do |post_image| %>
<div>
  <%= link_to post_image_path(post_image.id) do %>
    <%= attachment_image_tag post_image, :image %>
  <% end %>
  <p>投稿ユーザー画像：<%= attachment_image_tag post_comment.user, :profile_image, :fill, 60, 60, fallback: "no_image.jpg" %></p>
  <p>ショップ名：<%= post_image.shop_name %></p>
  <p>説明：<%= post_image.caption %></p>
  <p>ユーザーネーム：<%= post_image.user.name %></p>
  <p><%= link_to "#{post_image.post_comments.count} コメント", post_image_path(post_image.id) %></p>

</div>
<% end %>
<%= paginate @post_images %>