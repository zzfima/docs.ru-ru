---
title: "Список атрибутов (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a>Список атрибутов (Visual Basic)
Указывает атрибуты, применяемые к объявленных программных элементов. Несколько атрибутов разделяются запятыми. Ниже приведен синтаксис для одного атрибута.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Части  
 `attributemodifier`  
 Требуется для атрибутов, примененных в начале исходного файла. Может быть [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) или [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 `attributename`  
 Обязательный. Имя атрибута.  
  
 `attributearguments`  
 Необязательно. Список позиционных аргументов для этого атрибута. Несколько аргументов разделяются запятыми.  
  
 `attributeinitializer`  
 Необязательно. Список инициализаторов переменная или свойство для этого атрибута. Несколько инициализаторов разделяются запятыми.  
  
## <a name="remarks"></a>Примечания  
 Можно применить один или несколько атрибутов практически любого элементу программирования (типы, процедуры, свойства и т. д.). Атрибуты отображаются в метаданных сборки и они могут помочь комментировать код или указать способ использования конкретного программного элемента. Можно применить атрибутами, определенными по Visual Basic и .NET Framework, и можно определить собственные атрибуты.  

 Дополнительные сведения об использовании атрибутов см. в разделе [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md). Сведения о имена атрибутов см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Правила  
  
-   **Размещение.** Можно применить атрибуты к наиболее объявленных программных элементов. Чтобы применить один или несколько атрибутов, поместите *блок атрибута* в начале объявления элемента. Каждая запись в списке атрибутов задает атрибут, по которому вы хотите применить и модификатор и аргументы, которые вы используете для этого вызова атрибута.  
  
-   **Угловые скобки.** Если указан список атрибутов, его необходимо заключить в угловые скобки («`<`«и»`>`»).  
  
-   **Часть объявления.** Атрибут должен быть частью объявления элемента, а не отдельной инструкции. Можно использовать последовательность продолжения строки (» `_`«) для расширения оператора объявления на несколько строк исходного кода.  
  
-   **Модификаторы.** Модификатор атрибута (`Assembly` или `Module`) необходим для каждого атрибута, примененного к элементу программирования в начале исходного файла. Модификаторы атрибутов не допускаются для атрибутов, примененных к элементам, не находящиеся в начале файла исходного кода.  
  
-   **Аргументы.** Все позиционные аргументы атрибута должны предшествовать инициализаторам любой переменной или свойству.  
  
## <a name="example"></a>Пример  
 В следующем примере применяется <xref:System.Runtime.InteropServices.DllImportAttribute> атрибут определение схемы `Function` процедуры.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>Указывает, что процедура атрибутами представляет точку входа в неуправляемой библиотеки динамической компоновки (DLL). Атрибут предоставляет имя DLL как позиционные аргументы и другие сведения — как инициализаторы переменных.  
  
## <a name="see-also"></a>См. также  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [Module \<ключевое_слово>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
