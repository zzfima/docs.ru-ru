---
title: Функциональное и процедурное программирование (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: ea1015a5-d4c8-4d79-8e1e-ba17a40a4f39
ms.openlocfilehash: 3d1e3cf01b30454d29836f176afcd39cb2b55b73
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353415"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-visual-basic"></a>Functional vs. Procedural Programming (LINQ to XML) (Visual Basic)
XML-приложения имеют самые разнообразные типы.  
  
- Некоторые приложения принимают исходные XML-документы и представляют новые XML-документы в новой форме, отличной от формы исходных документов.  
  
- Некоторые приложения принимают исходные XML-документы и представляют документы совершенно в другом формате, например в виде кода HTML или текстовых файлов CSV.  
  
- Некоторые приложения принимают исходные XML-документы и вставляют записи в базу данных.  
  
- Некоторые приложения принимают данные из другого источника, например из базы данных, и создают из них XML-документы.  
  
 Это не все типы XML-приложений, а лишь представительный набор тех типов, которые приходится создавать программисту, работающему с кодом XML.  
  
 При всем разнообразии типов приложений существуют только два противоположных подхода, которыми может воспользоваться разработчик:  
  
- функциональное построение с использованием декларативного стиля;  
  
- модификация XML-дерева в оперативной памяти с использованием процедурного кода.  
  
 LINQ to XML поддерживает оба подхода.  
  
 При использовании функционального подхода вы должны написать преобразования исходных документов, чтобы получить совершенно новые документы нужного формата.  
  
 При изменении XML-дерева на месте вы должны написать код, который прослеживает узлы находящегося в памяти XML-дерева и переходит по ним, по мере необходимости вставляя, удаляя и изменяя узлы.  
  
 LINQ to XML можно использовать в обоих подходах. Используются одни и те же классы, а в некоторых случаях и одинаковые методы. Но организация и цели этих двух подходов существенно различаются. Например, в разных ситуациях один из них часто оказывается производительнее другого и использует больше или меньше памяти. Кроме того, код на основе одного или другого подхода легче писать, а сам код является более простым в обслуживании.  
  
 To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md).  
  
 For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).  
  
## <a name="see-also"></a>См. также

- [LINQ to XML Programming Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
