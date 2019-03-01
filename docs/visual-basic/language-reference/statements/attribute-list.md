---
title: Список атрибутов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: fb25ecad3b797a4993e7a780823a38a0f0ccbd1f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975632"
---
# <a name="attribute-list-visual-basic"></a>Список атрибутов (Visual Basic)
Указывает атрибуты, применяемые к объявленный программный элемент. Несколько атрибутов разделяются запятыми. Ниже приведен синтаксис для одного атрибута.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Части  
|||
|---|---|
|`attributemodifier`|Требуется для атрибутов, примененных в начале исходного файла. Может быть [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) или [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md).|
|`attributename`| Обязательный. Имя атрибута.|
|`attributearguments`|Необязательный параметр. Список позиционных аргументов для этого атрибута. Несколько аргументов разделяются запятыми.|
|`attributeinitializer`|Необязательный параметр. Список инициализаторов переменной или свойства для этого атрибута. Несколько инициализаторов разделяются запятыми.|
  
## <a name="remarks"></a>Примечания  
 Один или несколько атрибутов можно применить практически любой программный элемент (типы, процедуры, свойства и т. д.). Атрибуты отображаются в метаданных сборки и они могут помочь комментировать код или указать способ использования конкретного программного элемента. Можно применить атрибутами, определенными по Visual Basic и .NET Framework, и вы можете определить собственные атрибуты.  

 Дополнительные сведения об использовании атрибутов см. в разделе [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md). Сведения о имена атрибутов, см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Правила  
  
-   **Размещение.** Вы можете применять атрибуты к наиболее объявленных программных элементов. Чтобы применить один или несколько атрибутов, поместите *блок атрибутов* в начале объявления элемента. Каждая запись в списке атрибутов задает атрибут, который вы хотите применить и модификатор и аргументы, которые вы используете для этого вызова этого атрибута.  
  
-   **Угловые скобки.** Если указать список атрибутов, его необходимо заключить в угловые скобки (»`<`«и»`>`«).  
  
-   **Часть объявления.** Атрибут должен быть частью объявления элемента, а не отдельной инструкции. Можно использовать последовательность продолжения строки (» `_`«) для расширения оператора объявления на несколько строк исходного кода.  
  
-   **Модификаторы.** Модификатор атрибута (`Assembly` или `Module`) необходим для каждого атрибута, примененного к программному элементу в начале исходного файла. Атрибут модификаторы не могут быть указаны для атрибутов, примененных к элементам, которые не в начале исходного файла.  
  
-   **Аргументы.** Все позиционные аргументы для атрибута должны предшествовать инициализаторы любой переменной или свойству.  
  
## <a name="example"></a>Пример  
 В следующем примере применяется <xref:System.Runtime.InteropServices.DllImportAttribute> атрибут определение схемы `Function` процедуры.  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> Указывает, что процедура с атрибутами представляет точку входа в неуправляемой библиотеки динамической компоновки (DLL). Атрибут предоставляет имя DLL как позиционные аргументы и другие сведения, как инициализаторы переменных.  
  
## <a name="see-also"></a>См. также
- [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Module \<ключевое_слово>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
