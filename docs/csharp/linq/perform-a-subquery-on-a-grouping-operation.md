---
title: "Вложенный запрос в операции группирования"
description: "Сведения о выполнении вложенного запроса в операции группирования."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 68acc07e0c33d042123d3cd403a73d58a7c3d245
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Вложенный запрос в операции группирования

В этом разделе показаны два разных способа создания запроса, упорядочивающего исходные данные в группы и затем выполняющего вложенный запрос для каждой группы по отдельности. Основное действие в каждом примере заключается в группировании исходных элементов с помощью *продолжения* с именем `newGroup` с последующим созданием вложенного запроса для `newGroup`. Этот вложенный запрос выполняется для каждой новой группы, создаваемой внешним запросом. В этом конкретном примере следует обратить внимание на то, что в конечном итоге получается не группа, а простая последовательность анонимных типов.  
  
 Дополнительные сведения о способах группирования см. в разделе [Предложение group](../language-reference/keywords/group-clause.md).  
  
 Дополнительные сведения о продолжениях см. в разделе [into](../language-reference/keywords/into.md). В приведенном ниже примере в качестве источника данных используется структура данных в памяти, но те же принципы действуют для любого типа источника данных LINQ.  
  
## <a name="example"></a>Пример 

 > [!NOTE]
 > Этот пример содержит ссылки на объекты, определенные в примере кода в разделе [Запрос коллекции объектов](query-a-collection-of-objects.md).

 [!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a>См. также  
 [Выражения запросов LINQ](index.md)

