---
title: "Тип &quot;&lt;typename&gt;&quot; не определен | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 09aa7c535fd5e17ddcd0e743fb5ec17ebadd4f7d
ms.lasthandoff: 03/13/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Тип "&lt;typename&gt;" не определен
Инструкция делает ссылку на тип, который не был определен. Можно определить тип в операторе объявления таких как `Enum`, `Structure`, `Class`, или `Interface`.  
  
 **Идентификатор ошибки:** BC30002  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что определение типа и его ссылка использовать написания.  
  
-   Убедитесь, что определение типа доступно для ссылки. Например, если тип находится в другом модуле и был объявлен `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.  
  
-   Убедитесь, что пространство имен типа не переопределено в проекте. Если это так, используйте `Global` ключевое слово для полного имени типа. Например, если проект определяет пространство имен с именем `System`, <xref:System.Object?displayProperty=fullName>тип недоступен, если он не является полностью соответствовать `Global` ключевое слово: `Global.System.Object`.</xref:System.Object?displayProperty=fullName>  
  
-   Если тип определен, но библиотека объектов или библиотеки типов, в которой определен не зарегистрирован в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], нажмите кнопку **добавить ссылку** на **проекта** меню и выберите соответствующую библиотеку типов.  
  
-   Убедитесь, что тип в сборке, которая является частью целевого профиля .NET Framework. Дополнительные сведения см. в разделе [Устранение ошибок для различных версий .NET Framework](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>См. также  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Управление ссылками в проекте](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)
