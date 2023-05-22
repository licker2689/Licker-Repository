# Licker 라이브러리

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
