---
title: "Создание вложенной группы"
description: "Практическое руководство по созданию вложенной группы."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 361ac1f224c6eef292fcf8434c7e465c9448b19c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-nested-group"></a>Создание вложенной группы

В следующем примере демонстрируется создание вложенных групп в выражении запроса LINQ. Каждая группа, созданная в соответствии с годом обучения или курсом учащегося, затем подразделяется на группы по именам учащихся.  
  
## <a name="example"></a>Пример

 > [!NOTE]
 > Этот пример содержит ссылки на объекты, определенные в примере кода в разделе [Запрос коллекции объектов](query-a-collection-of-objects.md). 

 [!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 Обратите внимание, что для выполнения итерации по внутренним элементам вложенной группы необходимо три вложенных цикла `foreach`.  
  
## <a name="see-also"></a>См. также  
 [Выражения запросов LINQ](index.md)

