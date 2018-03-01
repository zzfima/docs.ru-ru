---
title: "Тип возвращаемого значения функции &#39; &lt;имя_процедуры&gt;&#39; не является CLS-совместимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 866c0001d51a2eff75409c3918a6b6189ca294d8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>Тип возвращаемого значения функции &#39; &lt;имя_процедуры&gt;&#39; не является CLS-совместимым
Объект `Function` процедура помечена как `<CLSCompliant(True)>` , но возвращает тип, который помечен как `<CLSCompliant(False)>`, не помечен или не квалифицирован, так как он имеет несоответствующий тип.  
  
 Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), процедура должна использовать только типы, соответствующие CLS. Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.  
  
 Следующие типы данных [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не соответствуют CLS:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40027  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если `Function` процедура должна возвращать этот конкретный тип, удалите <xref:System.CLSCompliantAttribute>. Процедура не может соответствовать CLS.  
  
-   Если `Function` процедура должна быть CLS-совместимыми, измените тип возвращаемого значения на ближайший CLS-совместимый тип. Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
-   При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Например, данные типа `int` часто являются 16-битными в других средах. Если возвращается 16-разрядное целое число такому компоненту, объявите его как `Short` вместо `Integer` в управляемом [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] кода.