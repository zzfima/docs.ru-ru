---
title: "Тип &#39; &lt;typename&gt;&#39; не определен"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords: BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68eb37f43600c51dc9117c3785a12e3c8ede1965
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Тип &#39; &lt;typename&gt;&#39; не определен
Инструкция представляет собой ссылку на тип, который не был определен. Можно определить тип в операторе объявления например `Enum`, `Structure`, `Class`, или `Interface`.  
  
 **Идентификатор ошибки:** BC30002  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что определения типа и его ссылки используют написания.  
  
-   Убедитесь, что определение типа доступно для ссылки. Например, если тип находится в другом модуле и был объявлен `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.  
  
-   Убедитесь, что пространство имен типа не переопределено в проекте. Если это так, используйте `Global` ключевое слово, чтобы указать полное имя типа. Например, если проект определяет пространство имен с именем `System`, <xref:System.Object?displayProperty=nameWithType> тип недоступен, если он не является полностью соответствовать `Global` ключевое слово: `Global.System.Object`.  
  
-   Если тип определен, но библиотека объектов или библиотеки типов, в которой определен не зарегистрирован в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], нажмите кнопку **добавить ссылку** на **проекта** меню, а затем выберите нужный объект Библиотека или библиотеки типов.  
  
-   Убедитесь, что тип в сборке, которая является частью целевого профиля .NET Framework. Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>См. также  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
