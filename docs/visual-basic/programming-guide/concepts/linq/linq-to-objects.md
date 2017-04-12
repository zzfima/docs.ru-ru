---
title: "LINQ to Objects (Visual Basic) | Документы Microsoft"
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
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d2bc048fea9affd4998430783d20b978317f3897
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
Термин «LINQ to Objects» относится к использованию LINQ запросы с любыми <xref:System.Collections.IEnumerable>или <xref:System.Collections.Generic.IEnumerable%601>коллекции напрямую, без использования промежуточного поставщика LINQ или API, такого как [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) или [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> Можно использовать LINQ для запросов любой перечислимой коллекции, например <xref:System.Collections.Generic.List%601>, <xref:System.Array>, или <xref:System.Collections.Generic.Dictionary%602>.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Array> </xref:System.Collections.Generic.List%601> Коллекции могут определяться пользователем или возвращенной .NET Framework API.  
  
 В общем смысле LINQ to Objects представляет новый подход к коллекциям. Раньше нужно было написать сложные циклы `For Each`, определяющие порядок извлечения данных из коллекции. Подход LINQ пишется декларативный код, описывающий, которые необходимо получить.  
  
 Кроме того, запросы LINQ имеют три основных преимущества по сравнению с традиционными `For Each` циклы:  
  
1.  Они более краткие и удобочитаемые, особенно при фильтрации нескольких условий.  
  
2.  Они предоставляют широкие возможности фильтрации, упорядочивания и группировки с минимумом кода приложения.  
  
3.  Они могут переноситься в другие источники данных практически без изменений.  
  
 В целом, чем более сложные операции, которую нужно выполнить с данными, тем больше преимуществ вы получаете при использовании LINQ вместо традиционных способов итерации.  
  
 Этот раздел предназначен для демонстрации подход LINQ с помощью нескольких примеров. Он не претендует на исчерпывающий характер.  
  
## <a name="in-this-section"></a>Содержание  
 [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 Содержит описание использования LINQ для запроса и преобразования строк и коллекций строк. Ссылки на разделы, демонстрирующие эти принципы.  
  
 [LINQ и отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 Ссылки на пример, демонстрирующий, как LINQ использует отражение.  
  
 [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Содержит описание использования LINQ для взаимодействия с файловыми системами. Ссылки на разделы, демонстрирующие эти понятия.  
  
 [Практическое руководство: запроса к ArrayList с помощью LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 Демонстрирует запроса ArrayList в C#.  
  
 [Практическое руководство: Добавление пользовательских методов для запросов LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 Объясняет, как расширить набор методов, которые можно использовать для запросов LINQ путем добавления методов расширения в <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601>  
  
 [Интегрированный в язык запрос (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Ссылки на разделы, в которых описание LINQ, а также примеры кода для выполнения запросов.
