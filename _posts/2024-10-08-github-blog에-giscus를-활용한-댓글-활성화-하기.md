---
layout: post
title: Github Blog에 giscus를 활용한 댓글 활성화 하기
date: 2024-10-08 10:32 +0900
description: Jekyll-Chirpy로 생성한 블로그에 giscus 사용하기
category: [GitHub, Blog]
tags: [GitHub, Jekyll, Chirpy, Blog, giscus, Comment, Discussion]
---
<hr>

> giscus에 대한 더욱 자세한 설명은 [https://giscus.app/ko](https://giscus.app/ko)에서 확인할 수 있습니다.
{: .prompt-tip }

<hr>

> ## __개요__

[giscus](https://giscus.app/ko)페이지의 설명에서 확인할 수 있듯이 giscus를 사용하기 위해서는 다음 **조건을 만족**하여야 합니다.

1. [공개](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility#making-a-repository-public) 저장소여야 합니다. 그렇지 않으면 방문자들은 Discussion을 볼 수 없습니다.
2. [giscus](https://github.com/apps/giscus) 앱이 설치되어 있어야 합니다. 그렇지 않으면 방문자들은 댓글과 반응을 남길 수 없습니다.
3. Discussions 기능이 [해당 저장소에서 활성화되어 있어야 합니다.](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/enabling-or-disabling-github-discussions-for-a-repository)

<hr>

> ## __giscus app 설치하기__

[https://github.com/apps/giscus](https://github.com/apps/giscus)에서 github에 로그인 한 후 giscus를 설치합니다.

![giscus_install.png](/assets/img/posts/giscus_install.png)

<hr>

> ## __Discussions 기능 활성화 하기__

댓글 기능을 사용할 저장소 ➜ Settings ➜ General ➜ Features ➜ Discussions 활성화

![discussions_enable.png](/assets/img/posts/discussions_enable.png)

<hr>

> ## __giscus 설정__

[giscus](https://giscus.app/ko) 에서 나머지 설정을 진행합니다.

**나의 Repository를 입력합니다.**

![giscus_repo.png](/assets/img/posts/giscus_repo.png)

**discussion 카테고리 및 연결 방법을 설정합니다.**

![giscus_set1.png](/assets/img/posts/giscus_set1.png)

**사용할 기능과 테마를 선택합니다.**

![giscus_set2.png](/assets/img/posts/giscus_set2.png)

**위의 값들을 기입하면 알맞은 scripts 태그를 확인할 수 있습니다.**
**이 태그를 템플릿에 추가하면 giscus 기능이 활성화 됩니다.**

![giscus_set3.png](/assets/img/posts/giscus_set3.png)

<hr>

> ## __config.yml에 추가__

Chirpy 테마에서는 위에서 발급받은 scripts 태그의 내용들을 _config.yml에 알맞게 기재하여 giscus를 사용할 수 있습니다.

![giscus_config.png](/assets/img/posts/giscus_config.png)

<hr>

> 오타가 발생하였거나 보완 할 부분이 있다면 댓글 남겨주시면 감사하겠습니다. 🙂
{: .prompt-tip }