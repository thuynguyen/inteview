class Post < ActiveRecord::Base
  validate :url_valid
  
  def url_valid
    valids = []
    conds = %w(www us ca jp http https com net)
    conds.each do |f|
      valids << url.include?(f)
    end
    errors.add(:url, "can't be in valid") if
      !valids.include?true
  end
  
  def format_url 
    if self.url.include?"http://www." 
      view_url = self.url.split("http://www.").last
      view_url = view_url.split("/").first
    elsif self.url.include?"https://www." 
      view_url = self.url.split("https://www.").last
      view_url = view_url.split("/").first
    elsif self.url.include?"https://" 
      view_url = self.url.split("https://www.").last
      view_url = view_url.split("/").first
    elsif self.url.include?"www."
      view_url = self.url.split("www.").last
      view_url = view_url.split("/").first
    elsif self.url.include?"/"
      view_url = self.url.split("/").first
    else
      view_url = self.url
    end
    return view_url
  end
end
