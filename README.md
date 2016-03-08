# android-style-guide
본 문서는 BBB Inc 구성원들의 Android 협업을 쉽고 명확하게 진행하기 위한 스타일 가이드입니다. 구성원들의 의사결정에 따라 수시로 변경될 수 있습니다.


## 목차
- [프로젝트 가이드라인](#프로젝트-가이드라인)
  - [패키지 아키텍쳐](#패키지-아키텍쳐)
  - [파일 네이밍](#파일-네이밍)
- [코드 가이드라인](#코드-가이드라인)
  - [네이밍](#네이밍)


## 프로젝트 가이드라인

### 패키지 아키텍쳐
- activitiy가 하나만 존재할 경우에는 패키지 내의 최상단에 두고, 그 이상은 별도의 activities 패키지에 둔다.

```java
com.bbbtech.project
├─ activities
├─ network
├─ models
├─ managers
├─ utils
├─ fragments
└─ views
   ├─ adapters
   ├─ actionbar
   ├─ widgets
   └─ notifications
```

### 파일 네이밍

#### 클래스 파일
클래스명은 UpperCamelCase를 사용합니다.
클래스가 Android Component를 extend할 경우, 클래스명은 Component 이름으로 끝나야 합니다.

`MainActivity`, `LoginFragment`, `AuthAlertDialog`, `ProtocolConnectionService`

#### Resource 파일
Resource 파일명은 lower_underscore를 사용합니다.

##### Drawable 파일

|Asset Type|Prefix|Example|
|----------|------|-------|
|Icons|`ic_`|`ic_launcher.png`|
|Images|`img`|`img_man_logo`|

##### Layout 파일
Layout 파일명은 관련된 Component로 시작합니다.

|Component|Example Class Name|Example File Name|
|---------|------------------|-----------------|
|Activity|`MainActivity`|`activity_main.xml`|
|Fragement|`ProgressFragment`|`fragment_progress.xml`|

##### Menu 파일
menu 파일은 menu 폴더 내에 위치하기 때문에 별도의 prefix 없이 사용되는 Component를 앞으로 보냅니다.

|Example Activity Name|Example File Name|
|---------------------|-----------------|
|`MainActivity`|`activity_main.xml`|

##### Values 파일
Values 폴더 내에 위치한 리소스 파일명은 복수형으로 사용합니다.

`strings.xml`, `colors.xml`, `dimens.xml`, `ui_colors.xml`


## 코드 가이드라인

### Java 언어 규칙

#### Don’t Ignore Exceptions

#### Don't catch generic exception

#### Don't use finalizers

### 네이밍

#### 변수

- 변수 이름은 lowerCamelCase를 사용합니다.
- 멤버 변수 이름에 접두사<sup>Prefix</sup> `m` 을 붙입니다.
- AndroidStudio에서 Preferences를 통해 Getter/Setter 생성 시에도 m이 처리 되도록 구현 할 수있습니다.
![Image of HowToSetPrefix](https://octodex.github.com/images/yaktocat.png)

#### 상수

- 상수 이름은 ALL_UPPER_CASE를 사용합니다.
- 각 단어는 underscore `_` 로 분리합니다.
- 상수 이름은 부가 설명 없이도 코드를 이해할 수 있게 작성해야 합니다.

**좋은 예**

```java
final int TAX_RATE = 0.03f;
final int WEDNESDAY = 3;
final int DAYS_IN_WEEK = 7;

…중략…

day = (WEDNESDAY + numberOfDays) % DAYS_IN_WEEK;
```

**나쁜 예**

```java
final int texRate;
final int TAXRATE;
final int DaysInWeek;

…중략…

day = (3 + numberOfDays) % 7;
```

#### 약어

- 약어는 항상 대문자로 표시합니다. (논의 필요)

**좋은 예**

```java
int userID;
int URLString;
int HTML;
```

**나쁜 예**

```java
int userId;
int urlString;
int html;
```
