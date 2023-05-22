# LIP 라이브러리


## 인증 설정

`gradle.properties` 파일에 아래 처럼 추가하세요
```properties
github.username=<당신의 깃허브 유저이름>
github.token=<당신의 깃허브 토큰>
```

## 그래들 예제

```gradle
repositories {
    maven { 
        url = 'https://raw.githubusercontent.com/LIP-licker-in-plugin/library-mirror/spigot-api-<버전>/'
        credentials {
            username providers.gradleProperty('github.username').get()
            password providers.gradleProperty('github.token').get()
        }
        authentication {
            digest(BasicAuthentication)
        } 
    }
    
}

dependencies {
    compileOnly 'org.spigotmc:spigot-api:<버전>-R0.1-SNAPSHOT'
}

```
