source 'https://rubygems.org'

gem 'jekyll', '~> 3.9.3'

group :jekyll_plugins do
    gem 'github-pages', '~> 228'
    gem "jekyll-sitemap"
    gem "jekyll-include-cache"
    gem 'jekyll-contentblocks'
    # https://github.com/heychirag/jekyll-google-photos/issues/14
    # https://stackoverflow.com/questions/2577346/how-to-install-gem-from-github-source
    # fix: https://stackoverflow.com/a/28442337
    gem 'jekyll-google-photos', git: 'https://github.com/cooked/jekyll-google-photos.git', branch: 'patch-1_jekyll-4'
    # TODO: this gets conflicting ruby 2
    #gem 'jekyll-target-blank'   # open external links in new window 
end
