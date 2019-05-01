---
title: Практическое руководство. Как хранить и повторно использовать запросы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
ms.openlocfilehash: 1aac20c3f9c421d353938a83b9e321d35abd244e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033648"
---
# <a name="how-to-store-and-reuse-queries"></a>Практическое руководство. Как хранить и повторно использовать запросы
При наличии приложения, которое неоднократно выполняет схожие по структуре запросы, можно существенно увеличить производительность, если скомпилировать запрос один раз и затем выполнить его несколько раз с различными параметрами. Например, приложению может потребоваться получение всех клиентов из определенного города; название города указывается пользователем в форме во время выполнения. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает использование *скомпилированных запросов* для этой цели.  
  
> [!NOTE]
>  Данный метод использования удобен для большинства случаев применения скомпилированных запросов. Возможны и другие методы. Например, скомпилированные запросы можно сохранить в качестве статических членов разделяемого класса, который расширяет код, созданный конструктором.  
  
## <a name="example"></a>Пример  
 Во многих сценариях может потребоваться повторно использовать запросы в разных потоках. В таких случаях особенно эффективным становится метод сохранения скомпилированных запросов в статических переменных. В следующем примере кода предполагается, что класс `Queries` предназначен для хранения скомпилированных запросов, а класс "Northwind" представляет строго типизированный класс <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>Пример  
 В настоящее время невозможно сохранить (в статических переменных) запросы, которые возвращают *анонимного типа*, так как у типа нет имени для предоставления как универсальный аргумент. В следующем примере демонстрируется, как можно решить эту проблему, создавая тип, представляющий результат, а затем используя его как универсальный аргумент.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.Linq.CompiledQuery>
- [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Запрос к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
