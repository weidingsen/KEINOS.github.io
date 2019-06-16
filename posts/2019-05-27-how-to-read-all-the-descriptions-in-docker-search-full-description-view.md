---
title: How to read all the descriptions in docker search (Full description view)
author: KEINOS
type: post
date: 2019-05-27T07:24:53+00:00
excerpt: docker search コマンドで検索時に DESCRIPTION を省略せずに、すべて表示させたい場合は "--no-trunc" オプションを使います。
url: /20190527_4563
yuzo_related_post_metabox:
  - 'a:3:{s:17:"yuzo_include_post";s:0:"";s:17:"yuzo_exclude_post";s:0:"";s:21:"yuzo_disabled_related";N;}'
outline_none:
  - 1
post_views_count:
  - 35
categories:
  - Docker
tags:
  - --no-trunc
  - docker search

---
> When `docker search`, the `DESCRIPTION` column in the results are truncated/trimmed but I want to view them fully. 

    $ docker search alpine | head -5
    NAME                                   DESCRIPTION                                     STARS               OFFICIAL            AUTOMATED
    alpine                                 A minimal Docker image based on Alpine Linux…   5332                [OK]                
    mhart/alpine-node                      Minimal Node.js built on Alpine Linux           431                                     
    anapsix/alpine-java                    Oracle Java 8 (and 7) with GLIBC 2.28 over A…   408                                     [OK]
    frolvlad/alpine-glibc                  Alpine Docker image with glibc (~12MB)          203                                     [OK]
    

## TL;DR {#outline__1}

> Use `--no-trunc` option 

    $ docker search --no-trunc alpine | head -5
    NAME                                   DESCRIPTION                                                                                            STARS               OFFICIAL            AUTOMATED
    alpine                                 A minimal Docker image based on Alpine Linux with a complete package index and only 5 MB in size!      5332                [OK]                
    mhart/alpine-node                      Minimal Node.js built on Alpine Linux                                                                  431                                     
    anapsix/alpine-java                    Oracle Java 8 (and 7) with GLIBC 2.28 over AlpineLinux                                                 408                                     [OK]
    frolvlad/alpine-glibc                  Alpine Docker image with glibc (~12
    

## TS;DR {#outline__2}

`docker search` で検索すると `DESCRIPTION` の内容が途中で切れてしまいます。全体を見たいのに、いちいち Docker Hub まで覗きにいくのも大変。また、イメージには含まれていないため、`docker inspect` でも確認できません。

「[`how` `to` `read` `all` `the` `description` `in` `docker` `search`][1]」とググっても、ドンピシャの内容が出てきませんでした。

    $ docker search --help
    
    Usage:  docker search [OPTIONS] TERM
    
    Search the Docker Hub for images
    
    Options:
      -f, --filter filter   Filter output based on conditions provided
          --format string   Pretty-print search using a Go template
          --limit int       Max number of search results (default 25)
          --no-trunc        Don't truncate output
    

なんと、、、普通に `help` にありました。あちょんぶりけ。

## 参考文献 {#outline__3}

  * [&#8220;Docker search and description column&#8221; のコメント][2] @ StackOverflow

 [1]: https://www.google.com/search?q=how+to+read+all+the+description+in+docker+search
 [2]: https://stackoverflow.com/a/53742438/8367711