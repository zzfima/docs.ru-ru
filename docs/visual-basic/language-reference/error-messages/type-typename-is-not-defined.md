---
title: "Тип &lt;имяТипа&gt; не определен | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30002"
  - "bc30002"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30002"
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип &lt;имяТипа&gt; не определен
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В операторе содержится ссылка на тип, который не был определен.  Можно определить тип в операторе объявления, например, `Enum`, `Structure` `Class` или `Interface`.  
  
 **Идентификатор ошибки:** BC30002  
  
### Чтобы исправить эту ошибку  
  
-   Проверьте правильность написания определения типа и ссылки на него.  
  
-   Убедитесь, что определение типа доступно для ссылки.  Например, если тип находится в другом модуле и был объявлен как `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.  
  
-   Убедитесь, что пространство имен типа не переопределено в проекте.  Если это так, используйте ключевое слово `Global` для полного указания имени типа.  Например, если проект определяет пространство имен с именем `System`, тип <xref:System.Object?displayProperty=fullName> не может быть доступен, пока он не будет полностью квалифицирован с использованием ключевого слова `Global` `Global.System.Object`.  
  
-   Если тип определен, но библиотека объектов или типов, в которой он определен, не зарегистрирована в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], щелкните **Add Reference** в меню **Project** и выберите необходимую библиотеку.  
  
-   Убедитесь, что тип принадлежит к сборке, являющейся частью целевого профиля .NET Framework.  Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visual-studio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## См. также  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Управление ссылками в проекте](/visual-studio/ide/managing-references-in-a-project)