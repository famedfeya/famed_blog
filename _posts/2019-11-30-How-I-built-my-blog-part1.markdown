---
layout: post
title:  "How I built my blog - Part 1"
date:   2019-11-30 15:41:33 +0100
categories: howtos
---

This is a post on how I set up this blog. I choose to use `Jekyll` and `GitHub Pages` to host the blog.

1.  Created a New GitHub repository as detailed in the instructions here [GitHub Pages][github-pages] 

    ![Creating a repository in GitHub pages](/images/2019-11-30 16_32_36-Create a New Repository.png)

2.  Installed Jekyll on my Windows 10 machine using [RubyInstaller with DevKit][rubyinstaller]

    The [Jekyll Windows Installation Instructions][jekyll-win-install] I followed are linked here.

3.  Verified that we had installed all the needed components: `Ruby`, `RubyGems` and `Jekyll`

    {% highlight ruby %}
    C:\Windows\System32>ruby -v
    ruby 2.6.5p114 (2019-10-01 revision 67812) [x64-mingw32]
    
    C:\Windows\System32>gem -v
    3.0.3
    
    C:\Windows\System32>jekyll -v
    jekyll 4.0.0
    {% endhighlight %}

4.  Navigated to the folder where I wanted to store a local copy of my blog and created my new jekyll site named `famed`
    
    {% highlight ruby %}
    C:\Windows\System32>cd "C:\Users\username\OneDrive\Blog"
    
    C:\Users\username\OneDrive\Blog>jekyll new famed
    Running bundle install in C:/Users/username/OneDrive/Blog/famed...
    Bundler: Fetching gem metadata from https://rubygems.org/...........
    Bundler: Fetching gem metadata from https://rubygems.org/.
    Bundler: Resolving dependencies...
    Bundler: Using public_suffix 4.0.1
    Bundler: Using addressable 2.7.0
    Bundler: Using bundler 2.0.2
    Bundler: Using colorator 1.1.0
    Bundler: Using concurrent-ruby 1.1.5
    Bundler: Using eventmachine 1.2.7 (x64-mingw32)
    Bundler: Using http_parser.rb 0.6.0
    Bundler: Using em-websocket 0.5.1
    Bundler: Using ffi 1.11.3 (x64-mingw32)
    Bundler: Using forwardable-extended 2.6.0
    Bundler: Using i18n 1.7.0
    Bundler: Using sassc 2.2.1 (x64-mingw32)
    Bundler: Using jekyll-sass-converter 2.0.1
    Bundler: Using rb-fsevent 0.10.3
    Bundler: Using rb-inotify 0.10.0
    Bundler: Using listen 3.2.0
    Bundler: Using jekyll-watch 2.2.1
    Bundler: Using kramdown 2.1.0
    Bundler: Using kramdown-parser-gfm 1.1.0
    Bundler: Using liquid 4.0.3
    Bundler: Using mercenary 0.3.6
    Bundler: Using pathutil 0.16.2
    Bundler: Using rouge 3.13.0
    Bundler: Using safe_yaml 1.0.5
    Bundler: Using unicode-display_width 1.6.0
    Bundler: Using terminal-table 1.8.0
    Bundler: Using jekyll 4.0.0
    Bundler: Fetching jekyll-feed 0.13.0
    Bundler: Installing jekyll-feed 0.13.0
    Bundler: Fetching jekyll-seo-tag 2.6.1
    Bundler: Installing jekyll-seo-tag 2.6.1
    Bundler: Fetching minima 2.5.1
    Bundler: Installing minima 2.5.1
    Bundler: Fetching thread_safe 0.3.6
    Bundler: Installing thread_safe 0.3.6
    Bundler: Fetching tzinfo 1.2.5
    Bundler: Installing tzinfo 1.2.5
    Bundler: Fetching tzinfo-data 1.2019.3
    Bundler: Installing tzinfo-data 1.2019.3
    Bundler: Fetching wdm 0.1.1
    Bundler: Installing wdm 0.1.1 with native extensions
    Bundler: Bundle complete! 6 Gemfile dependencies, 34 gems now installed.
    Bundler: Use `bundle info [gemname]` to see where a bundled gem is installed.
    New jekyll site installed in C:/Users/username/OneDrive/Blog/famed.
    {% endhighlight %}
    
5. 	Verified that files had been created 
    
    {% highlight ruby %}
    C:\Users\username\OneDrive\Blog\famed>dir
    Volume in drive C has no label.
    Volume Serial Number is 508E-A470
    
    Directory of C:\Users\username\OneDrive\Blog\famed
    
    30/11/2019  12:28    <DIR>          .
    30/11/2019  12:28    <DIR>          ..
    30/11/2019  12:27                56 .gitignore
    30/11/2019  12:27               419 404.html
    30/11/2019  12:27               539 about.markdown
    30/11/2019  12:27             1,156 Gemfile
    30/11/2019  12:28             2,014 Gemfile.lock
    30/11/2019  12:27               175 index.markdown
    30/11/2019  12:27             2,080 _config.yml
    30/11/2019  12:27    <DIR>          _posts
                   7 File(s)          6,439 bytes
                   3 Dir(s)  73,231,400,960 bytes free
    {% endhighlight %}		   
6.  Initiated the local `jekyll` server 
    
    {% highlight ruby %}
    C:\Users\username\OneDrive\Blog\famed>jekyll serve --watch
    Configuration file: C:/Users/username/OneDrive/Blog/famed/_config.yml
                Source: C:/Users/username/OneDrive/Blog/famed
           Destination: C:/Users/username/OneDrive/Blog/famed/_site
     Incremental build: disabled. Enable with --incremental
          Generating...
           Jekyll Feed: Generating feed for posts
                        done in 1.104 seconds.
     Auto-regeneration: enabled for 'C:/Users/username/OneDrive/Blog/famed'
        Server address: http://127.0.0.1:4000/
      Server running... press ctrl-c to stop.
    {% endhighlight %}	
7.  Modified the default configurations in the `_config.yml` file with my details
    
    {% highlight ruby %}
    title: My Tech Entries
    email: famedfeya at gmail com
    description: >- # this means to ignore newlines until "baseurl:"
            Walk with me in this random journey of discovery
    baseurl: "" # the subpath of your site, e.g. /blog
    url: "https://famedfeya.github.io" 
    twitter_username: elmknyk
    github_username:  famedfeya
    {% endhighlight %}	
    
    Since we modified the config file, we need to reinitialize the server again.
    
    {% highlight ruby %}
    C:\Users\username\OneDrive\Blog\famed>jekyll serve --watch
    {% endhighlight %}	
    
8.  At this point, I tried a couple of theme customization options but got a little confused. I will therefore skip the customization for now and leave that for a separate blog post once I get my blog up and running. 

9.  Added my first blog post 

    The posts  should all be added in the `_posts` directory saved in the format `YEAR-MONTH-DAY-title.MARKUP` and must begin with front matter to set a layout or other meta data. Here is an example    
    
    {% highlight ruby %}
    ---
    layout: post
    title:  "How I built my blog"
    date:   2019-11-30 15:41:33 +0100
    categories: howto
    tags: jekyll, github, blog
    ---
    This is the new blog text
    {% endhighlight %}	

10.  Updated my `About` page info

    {% highlight ruby %}
    ---
    layout: page
    title: About 
    permalink: /about/
    ---
    This is not a good about me example
    {% endhighlight %}	
    
    [github-pages]: https://pages.github.com/
    [jekyll-win-install]: https://jekyllrb.com/docs/installation/windows/
    [rubyinstaller]: https://rubyinstaller.org/downloads/


