# Jak sklonować branch ze zdalnego repozytorium

Załóżmy, że sklonowaliśmy sobie zdalne repozytorium i chcemy sprawdzić jakie branche (także zdalne) są w repozytorium:
Uruchamiamy $ git branch z flagą `-a`:

```
    $ git branch -a
    * master
      origin/HEAD
      origin/master
      origin/change-20
      origin/feature-1
```
Jeśli jest już istniejące repozytorium, ale pojawił się nowy branch można użyć $ git fetch

```
    git fetch
```
Aby zajrzeć do brancha na liście można bezpośrednio wpisać:
```
    $ git checkout origin/feature-1
```
Aby pracować na tym branchu trzeba uruchomić go lokalnie:
```
    $ git checkout -b feature-1 origin/feature-1
```
Teraz wyświetla się on jako lokalny branch
```
    $ git branch
      master
    * feature-1
```
Można śledzić (Track) więcej niż jedno repozytorium zdalne używając `git remote`.
```
    $ git remote add win32 git://example.com/users/joe/myproject-win32-port
    $ git branch -a
    * master
      origin/HEAD
      origin/master
      origin/change-20
      origin/feature-1
      win32/master
      win32/new-widgets
```
Uruchom `gitk` aby sprawdzić wszystkie refsy (branche, tagi, etc.).
```
    $ gitk --all &
```

zaczerpnięte z : https://gist.github.com/fabianmoronzirfas/4023446
