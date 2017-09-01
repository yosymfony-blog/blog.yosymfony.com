## Yo! Symfomy blog

This blob is based on [Clean blog theme](https://github.com/spress-add-ons/Clean-blog-theme).

### How to install?

* [Fork this repository](https://github.com/yosymfony-blog/blog.yosymfony.com/fork)
* Clone it: `git clone` https://github.com/YOUR-USER/blog.yosymfony.com.git
* Go to `blog.yosymfony.com` folder
* Run `spress site:build --server --watch`

### Writing a post

To create a new post, runs `new:post` command from Spress:

```bash
$ spress new:post
```

Each post could has a header image. You can configure your image and some data about it.

```yaml
header_img:
  url: "assets/img/post-bg-07.jpg"
  author: "Yuri Samoilov"
  author_url: "https://flic.kr/p/mjhDwB"
```

## License

[Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0).

## Icon sets
* [David Cross](http://webhostingmedia.net/). [Iconfinder profile](https://www.iconfinder.com/webhostingmedia).
* [Erik Ragnar Eliasson](https://www.iconfinder.com/iconsets/designer-skills)
