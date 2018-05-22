---
title: Protected Private (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a>Protected Private (Visual Basic)

`Private Protected` Сочетание ключевых слов — это модификатор доступа члена. Объект `Private Protected` член доступны все элементы в его вмещающий класс, а также по типам, производным от содержащего класса, но только если они находятся в его содержащей его сборки. 

Можно указать `Private Protected` только для членов классов; не удается применить `Private Protected` к членам структуры, так как структуры не наследуется.

`Private Protected` Модификатор доступа поддерживается по 15,5 Visual Basic и более поздних версий. Чтобы использовать его, можно добавить следующий элемент в файл проекта (*.vbproj) Visual Basic. При условии, что 15,5 Visual Basic или более поздней версии установлена в системе, она позволяет воспользоваться преимуществами возможности языка, поддерживаемые в последней версии компилятора Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> В Visual Studio, выбрав Справка F1 на `private protected` предоставляет справку для любого [закрытый](private.md) или [защищенных](protected.md). Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.

## <a name="rules"></a>Правила

- **Контекст объявления.** Можно использовать `Private Protected` только на уровне класса. Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейса, модуля, структуры или процедуры.

## <a name="behavior"></a>Поведение

- **Уровень доступа.** Весь код в классе можно получить доступ к его элементам. Код в любой класс, производный от базового класса, содержащихся в той же сборке может получать доступ ко всем `Private Protected` элементы базового класса. Тем не менее, код в любой класс, производный от базового класса, а также содержится в другой сборке не может получить доступ к базовым классом `Private Protected` элементов.

- **Модификаторы доступа.** Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*. Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).
  
 Модификатор `Private Protected` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) вложенного класса  
  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) делегата, вложенные в классе  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md) eumeration вложенной в классе 
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) интерфейса вложены в класс 
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Структура инструкции](../../../visual-basic/language-reference/statements/structure-statement.md) структуры, вложенные в классе 
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[Friend](friend.md)   
[Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
[Protected Friend](./protected-friend.md)   
[Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
