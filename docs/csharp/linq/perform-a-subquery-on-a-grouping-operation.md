---
title: "Вложенный запрос в операции группирования"
description: "Сведения о выполнении вложенного запроса в операции группирования."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c2c95479db10d81e748349e156f2314a6d4fccf
ms.lasthandoff: 03/13/2017

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
