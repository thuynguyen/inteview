class PostsController < ApplicationController
  
  def new
    @posts = Post.all(:order => "created_at DESC")
    @post = Post.new
  end

 
  def create
    @post = Post.new(params[:post])
    
    respond_to do |format|
      if @post.save
        format.js
      else
        format.html { render :action => "new" }
      end
    end
    @posts = Post.all(:order => "created_at DESC")
  end

end
