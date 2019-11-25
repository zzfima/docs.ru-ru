---
ms.openlocfilehash: be9a79f6ead3e72d7ffaade758704f0c1e2477f0
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394020"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a>Размещение. Универсальный узел ограничивает внедрение через конструктор Startup

Универсальный узел поддерживает для внедрения через конструктор класса `Startup` только типы `IHostEnvironment`, `IWebHostEnvironment` и `IConfiguration`. Это не влияет на приложения, которые используют `WebHost`.

#### <a name="change-description"></a>Описание изменений

До версии ASP.NET Core 3.0 можно было использовать внедрение конструктора для применения произвольных типов в конструкторе класса `Startup`. Начиная с ASP.NET Core 3.0 веб-стек переведен на универсальную библиотеку узлов. Эти изменения можно увидеть в файле *Program.cs* следующих шаблонов:

**ASP.NET Core 2.x:**

<https://github.com/aspnet/AspNetCore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

**ASP.NET Core 3.0:**

<https://github.com/aspnet/AspNetCore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

`Host` использует контейнер внедрения зависимостей для сборки приложения. `WebHost` использует два контейнера: один для узла и один для приложения. В результате конструктор `Startup` теперь не поддерживает внедрение пользовательской службы. Можно внедрять только `IHostEnvironment`, `IWebHostEnvironment` или `IConfiguration`. Это изменение предотвращает такие проблемы, как дублирование создания одноэлементной службы.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Это изменение является следствием перевода веб-стека на универсальную библиотеку узлов.

#### <a name="recommended-action"></a>Рекомендуемое действие

Внедряйте службы в подпись метода `Startup.Configure`. Например:

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
