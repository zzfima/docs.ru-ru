---
title: "Практическое руководство: запрос знаков в строке (LINQ) (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dabd63e52707f3078c6cdc41db8c4f0e7dfbf70e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a>Практическое руководство: запрос знаков в строке (LINQ) (Visual Basic)
Поскольку <xref:System.String>класс реализует универсальный <xref:System.Collections.Generic.IEnumerable%601>интерфейс, любая строка может запрашиваться как последовательность знаков.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.String> Однако это не часто используются LINQ. Для операций соответствия сложному шаблону используйте <xref:System.Text.RegularExpressions.Regex>класс.</xref:System.Text.RegularExpressions.Regex>  
  
## <a name="example"></a>Пример  
 В следующем примере запрашивается строки, чтобы определить количество цифр, содержащихся в нем. Обратите внимание, что запрос является «повторно» после выполнения первоначальной. Это возможно, поскольку сам запрос не хранит фактических результатов.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.  
  
## <a name="see-also"></a>См. также  
 [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [Практическое руководство: объединение запросов LINQ с регулярными выражениями (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
