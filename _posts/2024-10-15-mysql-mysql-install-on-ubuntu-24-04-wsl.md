---
layout: post
title: "[MySQL] MySQL Install on Ubuntu-24.04 (WSL)"
date: 2024-04-25 10:10 +0900
description:
category: [ Database, MySQL ]
tags: [ Database, MySQL, RDBMS, WSL, Ubuntu ]
---
<hr>

> 본 포스팅에서는 Windows11 환경에서 WSL2를 사용하여 로컬 환경을 구성하였습니다.<br>
> WSL2 및 Ubuntu 24.04 LTS 설치방법은 [**여기**](https://j-hjin.github.io/posts/windows-11-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C-wsl-2-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0-ubuntu-24-04-lts/)에서 확인할 수 있습니다.
{: .prompt-tip }

<hr>

## __개요__

MySQL은 오픈소스이고 여러 *관계형 데이터베이스 관리 시스템* (RDBMS) 중 가장 잘 알려진 소프트웨어입니다.

Ubuntu-24.04에서 MySQL을 설치하고 계정을 추가하는 방법을 포스팅하려고 합니다.

Program|Version|Reference
:---:|:---:|:---:
MySQL|8.0.39-0ubuntu0.24.04.2|
Windows 11 Home|23H2|-
WSL|2|[https://learn.microsoft.com/ko-kr/windows/wsl/](https://learn.microsoft.com/ko-kr/windows/wsl/)
Ubuntu|24.04 LTS|

<hr>

## __MySQL 설치하기__

Ununtu 쉘에서 다음 명령줄을 통해 mysql-server를 설치합니다.

```bash
sudo apt-get update
sudo apt-get install mysql-server
```

설치가 완료 된 이후에는 mysql 데몬을 실행시킨 후 접근합니다.

```bash
sudo service mysql start
sudo mysql
```

```sql
select version();
```

정상적으로 mysql 버전이 출력된다면 성공입니다.

이후 root가 아닌 사용자 계정을 생성합니다.

```sql
CREATE USER 'hj@%' IDENTIFIED BY '12345';
GRANT ALL PRIVILEGES ON *.* TO 'hj@%';
```

접속이 정상적으로 되는지 확인합니다.

```bash
mysql -u hj -p
```

## __Trouble Shooting__

오류 발생 시 댓글 남겨주시면 향후 추가하도록 하겠습니다.

### __su: warning: cannot change directory to /nonexistent: No such file or directory__

```bash
sudo service mysql stop
sudo usermod -d /var/lib/mysql/ mysql
sudo service mysql start
```

<hr>

> 보완 할 부분이 있다면 댓글 남겨주시면 감사하겠습니다. 🙂
{: .prompt-tip }