---
title: Настройка перенаправления привязки сборок
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
ms.openlocfilehash: 5b24d99aa23358272eecd042c40001413965d7f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181685"
---
# <a name="configuring-assembly-binding-redirection"></a>Настройка перенаправления привязки сборок
По умолчанию приложение использует набор сборок .NET Framework, поставляемых вместе с версией среды выполнения, которая использовалась для компиляции приложения. Чтобы перенаправить ссылки привязки сборок на определенную версию сборок .NET Framework, можно использовать атрибут **appliesTo** элемента [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) в файле конфигурации приложения. Этот необязательный атрибут содержит номер версии .NET Framework, к которой применяется перенаправление. Если атрибут **appliesTo** не указан, элемент **\<assemblyBinding>** применяется ко всем версиям платформы .NET Framework.  
  
 Атрибут **appliesTo** появился в .NET Framework 1.1; он игнорируется в .NET Framework 1.0. Это означает, что при использовании платформы .NET Framework версии 1.0 применяются все элементы **\<assemblyBinding>** , даже если атрибут **appliesTo** задан.  
  
> [!NOTE]
> Используйте атрибут **appliesTo**, чтобы ограничить перенаправление привязки сборки лишь определенной версией среды выполнения.  
  
 Например, чтобы перенаправить привязку сборки .NET Framework версии 1.0, следует включить в файл конфигурации приложения приведенный ниже код XML.  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 Элементы **\<assemblyBinding>** учитывают порядок. Сначала следует вводить сведения о перенаправлении привязок для сборок .NET Framework версии 1.0, а затем для сборок .NET Framework версии 1.1. И только после этого вводятся сведения о перенаправлении привязок для любых перенаправлений сборок .NET Framework, которые не используют атрибут **appliesTo** и поэтому применимы ко всем версиям .NET Framework. В случае конфликта перенаправления используется первый подходящий оператор перенаправления в файле конфигурации.  
  
 Например, чтобы перенаправить одну ссылку на сборку .NET Framework 1.0, а другую ссылку — на сборку .NET Framework 1.1, можно использовать шаблон, показанный в псевдокоде ниже.  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">
  <!-- .NET Framework version 1.0 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">
  <!-- .NET Framework version 1.1 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="...">
  <!-- Redirects meant for all versions of the .NET Framework. -->
</assemblyBinding>  
```  
  
## <a name="debugging-configuration-file-errors"></a>Отладка файлов конфигурации  
 Среда выполнения анализирует файлы конфигурации один раз при создании домена приложения и загружает код в этот домен. Среда CLR обрабатывает ошибки в файле конфигурации, игнорируя данную запись. Среда выполнения игнорирует весь файл конфигурации, если он содержит неправильный код XML. Что касается недопустимого кода XML, игнорируются только недопустимые разделы.  
  
 Чтобы определить, используется ли файл конфигурации, можно проверить, происходит ли перенаправление привязки сборки. Чтобы узнать, какие сборки загружаются, используйте [средство просмотра журнала привязки сборок (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md). Чтобы просмотреть все привязки сборок, необходимо создать запись для параметра **ForceLog** в реестре.  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Включение и отключение автоматического перенаправления привязки](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
