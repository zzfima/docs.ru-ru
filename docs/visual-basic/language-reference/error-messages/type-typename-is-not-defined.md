---
title: Тип <typename> не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 80a3d31a8a46ce616be2dd2ab27faf0af04876f2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275085"
---
# <a name="type-typename-is-not-defined"></a>Тип "\<typename >" не определен
Инструкция содержится ссылка на тип, который не был определен. Можно определить тип в операторе объявления таких как `Enum`, `Structure`, `Class`, или `Interface`.  
  
 **Идентификатор ошибки:** BC30002  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что определение типа и его ссылка используется написания.  
  
-   Убедитесь, что определение типа доступно для ссылки. Например, если тип находится в другом модуле и был объявлен `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.  
  
-   Убедитесь, что пространство имен типа не переопределено в проекте. Если это так, используйте `Global` ключевое слово для задания полного имени типа. Например, если проект определяет пространство имен с именем `System`, <xref:System.Object?displayProperty=nameWithType> типа невозможен, если он не является полным образом `Global` ключевое слово: `Global.System.Object`.  
  
-   Если тип определен, но библиотека объектов или библиотеки типов, в котором он определен, не зарегистрирована в Visual Basic, щелкните **добавить ссылку** на **проекта** меню, а затем выберите соответствующий объект Библиотека или библиотеки типов.  
  
-   Убедитесь, что тип в сборке, которая является частью целевого профиля .NET Framework. Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>См. также
- [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
