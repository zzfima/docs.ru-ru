---
title: Тип &#39; &lt;typename&gt; &#39; не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 20f36a06000d0197ad80b83766f6612a474d5758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595190"
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Тип &#39; &lt;typename&gt; &#39; не определен
Инструкция представляет собой ссылку на тип, который не был определен. Можно определить тип в операторе объявления например `Enum`, `Structure`, `Class`, или `Interface`.  
  
 **Идентификатор ошибки:** BC30002  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что определения типа и его ссылки используют написания.  
  
-   Убедитесь, что определение типа доступно для ссылки. Например, если тип находится в другом модуле и был объявлен `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.  
  
-   Убедитесь, что пространство имен типа не переопределено в проекте. Если это так, используйте `Global` ключевое слово, чтобы указать полное имя типа. Например, если проект определяет пространство имен с именем `System`, <xref:System.Object?displayProperty=nameWithType> тип недоступен, если он не является полностью соответствовать `Global` ключевое слово: `Global.System.Object`.  
  
-   Если тип определен, но библиотека объектов или библиотеки типов, в которой определен не зарегистрирован в Visual Basic, щелкните **добавить ссылку** на **проекта** меню, а затем выберите нужный объект Библиотека или библиотеки типов.  
  
-   Убедитесь, что тип в сборке, которая является частью целевого профиля .NET Framework. Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>См. также  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
