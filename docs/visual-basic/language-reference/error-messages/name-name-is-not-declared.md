---
title: Имя <name> не объявлено
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3aadc49f91021409123550ba2712f1acf5b99d83
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260149"
---
# <a name="name-name-is-not-declared"></a>Имя "\<имя >" не объявлена
Оператор ссылается на элемент программирования, но компилятор не может найти элемент с указанным именем.  
  
 **Идентификатор ошибки:** BC30451  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Проверьте правильность написания в ссылающемся операторе. Visual Basic регистр не учитывается, но любое другое изменение в орфографии рассматривается как полностью другое имя. Обратите внимание, что символ подчеркивания (`_`) является частью имени и, следовательно, частью орфографии.  
  
2. Убедитесь, что оператор доступа к членам (`.`) между объектом и его членах. Например, если у вас есть элемент управления <xref:System.Windows.Forms.TextBox> с именем `TextBox1`, то для доступа к его свойству <xref:System.Windows.Forms.TextBoxBase.Text%2A> следует ввести `TextBox1.Text`. Если вместо этого ввести `TextBox1Text`, будет создано другое имя.  
  
3. Если правильность написания и имеет правильный синтаксис любого доступа к членам объекта, убедитесь, что элемент был объявлен. Дополнительные сведения см. в разделе [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).  
  
4. Если программный элемент объявлен, проверьте, что он находится в области. Если ссылающийся оператор находится вне области объявления программного элемента, может потребоваться уточнение имени элемента. Для получения дополнительной информации см. [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).  

5. Если вы не используете полное имя типа или типа и имени элемента (например, ваш код ссылается на свойство как `MethodInfo.Name` вместо `System.Reflection.MethodInfo.Name`), добавьте [оператор Imports](../statements/imports-statement-net-namespace-and-type.md).

6. При попытке компиляции стиле пакетов SDK для проекта (проект с \*VBPROJ-файл, который начинается со строки `<Project Sdk="Microsoft.NET.Sdk">`) и сообщение об ошибке ссылается на тип или член в сборке Microsoft.VisualBasic.dll, Настройка приложения для Компиляция со ссылкой на библиотеку времени выполнения Visual Basic. По умолчанию подмножество библиотеки внедряется в сборку в стиле пакетов SDK для проекта.

   Например, в следующем примере выполняется компиляции, поскольку <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> не удается найти метод. Он не внедрен в часть среды выполнения Visual Basic, в состав приложения.  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   Чтобы устранить эту ошибку, добавьте `<VBRuntime>Default</VBRuntime>` элемент в проекты `<PropertyGroup>` разделе описано, как показано в следующем файле проекта Visual Basic.

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a>См. также

- [Сводка по объявлениям и константам](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
