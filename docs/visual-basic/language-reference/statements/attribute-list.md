---
title: "Атрибут списка (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e360794ad217784e2358967bfbcc03959cd043b1
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="attribute-list-visual-basic"></a>Список атрибутов (Visual Basic)
Указывает атрибуты, применяемые к объявленному программному элементу. Несколько атрибутов разделяются запятыми. Ниже приведен синтаксис для одного атрибута.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Части  
 `attributemodifier`  
 Обязательный для атрибутов, примененных в начале исходного файла. Может быть [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) или [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 `attributename`  
 Обязательный. Имя атрибута.  
  
 `attributearguments`  
 Необязательный. Список позиционных аргументов для этого атрибута. Несколько аргументов разделяются запятыми.  
  
 `attributeinitializer`  
 Необязательный. Список инициализаторов переменных или свойств для данного атрибута. Несколько инициализаторов разделяются запятыми.  
  
## <a name="remarks"></a>Примечания  
 Можно применить один или несколько атрибутов практически любого элементу программирования (типы, процедуры, свойства и т. д.). Атрибуты отображаются в метаданных сборки и они могут помочь комментировать код или указать способ использования конкретного элемента программирования. Можно применить атрибуты, определенные в Visual Basic и .NET Framework, и можно определить собственные атрибуты.  

 Дополнительные сведения об использовании атрибутов см. в разделе [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md). Сведения об именах атрибутов в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Правила  
  
-   **Размещение.** Можно применить атрибуты к большинству объявленных элементов программирования. Чтобы применить один или несколько атрибутов, поместите *блок атрибута* в начале объявления элемента. Каждая запись в списке атрибутов задает атрибут, который вы хотите применить и модификатор и аргументы, которые вы используете для этого вызова этого атрибута.  
  
-   **Угловые скобки.** Если указан список атрибутов, его необходимо заключить в угловые скобки («`<`«и»`>`»).  
  
-   **Часть объявления.** Атрибут должен быть частью объявления элемента, а не отдельной инструкции. Можно использовать последовательность продолжения строки (« `_`») для расширения оператора объявления на несколько строк исходного кода.  
  
-   **Модификаторы.** Модификатор атрибута (`Assembly` или `Module`) необходим для каждого атрибута, примененного к элементу программирования в начале исходного файла. Модификаторы атрибутов не допускаются для атрибутов, примененных к элементам, которые не в начале исходного файла.  
  
-   **Аргументы.** Все позиционные аргументы атрибута должны предшествовать инициализаторам любой переменной или свойству.  
  
## <a name="example"></a>Пример  
 В следующем примере применяется <xref:System.Runtime.InteropServices.DllImportAttribute>атрибут определение схемы `Function` процедуры.</xref:System.Runtime.InteropServices.DllImportAttribute>  
  
 [!code-vb[VbVbalrStatements&#1;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>Указывает, что процедура атрибутами представляет точку входа в неуправляемой библиотеки динамической компоновки (DLL).</xref:System.Runtime.InteropServices.DllImportAttribute> Атрибут предоставляет имя DLL как позиционные аргументы и другие сведения — как инициализаторы переменных.  
  
## <a name="see-also"></a>См. также  
 [Сборки](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Модуль \<ключевое слово настроек](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

