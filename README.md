# Как добавить свой пакет в "магазин" Evolution CMS

## Требования к пакету
- Пакет должен быть зарегистрирован на [Packagist.org](https://packagist.org)
- Должен быть совместим с Evolution CMS 3.x
- Должен иметь открытый исходный код на GitHub

## Процесс добавления

### 1. Подготовьте пакет
Убедитесь что ваш `composer.json` содержит:
```json
{
  "name": "ваше-имя/название-пакета",
  "description": "Описание пакета",
}
```
### 2. Добавьте информацию о пакете

Вариант 1: Сделайте Fork этого репозитория и добавьте ваш пакет в packages.json 

Вариант 2: Через Issue с следующим шаблоном

```
Название пакета: 
Composer имя: vendor/package
GitHub репозиторий: 
Описание: 
Категории: 
Теги: 
```

### 3. Создайте Pull Request

### 4. Что происходит при установке

Когда пользователь нажимает "Установить":

1. **Package Navigator** берет `composer_name` из packages.json
2. **Вызывает** `$this->packageService->installPackage($composerName)`
3. **Composer** устанавливает пакет из Packagist
4. **Evolution CMS** автоматически регистрирует ServiceProvider

## 5. Пример успешного пакета

```json
    {
      "name": "AI Bot", 
      "description": "Модуль искусственного интеллекта для Evolution CMS",
      "type": "module / plugin",
      "repository": "https://github.com/Kolya1222/ai_bot",
      "composer_name": "kolya2320/botai",
      "categories": ["ai", "automation"],
      "tags": ["ai", "bot", "automation", "module" ,"MCP"],
      "author": "roilafx",
      "documentation_url": "https://github.com/Kolya1222/ai_bot"
    }
