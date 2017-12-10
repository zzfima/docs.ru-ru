---
title: "&lt;proceduresignature1&gt; не является CLS-совместимым, поскольку он перегружает &lt;proceduresignature2&gt; которого отличается от него только массивом типов параметров массива или рангом типов параметра массива"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords: BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cdbd8edaefba4554e8de92cb600f045dc39f780
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt; не является CLS-совместимым, поскольку он перегружает &lt;proceduresignature2&gt; которого отличается от него только массивом типов параметров массива или рангом типов параметра массива
Процедура или свойство помечено как `<CLSCompliant(True)>` когда оно переопределяет другую процедуру или свойство, и единственное различие между их списки параметров вложенный уровень массива массивов или ранг массива.  
  
 В следующих объявлениях второе и третье объявления создают эту ошибку.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 Второе объявление изменяет исходный одномерный параметр `arrayParam` для массива массивов. Третье объявление превращает `arrayParam` двухмерный массив (ранг 2). Хотя Visual Basic допускает перегрузки, отличающиеся только одно из этих изменений, такая перегрузка не соответствует [независимость от языка и независимые от языка компоненты](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS).  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40035  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если требуется CLS-совместимость, определите перегрузки, отличающиеся друг от друга шире, чем представлено на этой странице справки.  
  
-   Если требуется, чтобы перегрузки отличались только по признакам, описанным в этой справке страницы, удалите <xref:System.CLSCompliantAttribute> из их определения или пометьте их как `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>См. также  
 [\<PAVE НАД > написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)  
 [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)
