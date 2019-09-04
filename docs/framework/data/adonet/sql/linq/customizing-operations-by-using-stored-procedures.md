---
title: Настройка операций за счет хранимых процедур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
ms.openlocfilehash: 63f4cb3cbb90afc37629b336972b5e09d20346b3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247533"
---
# <a name="customizing-operations-by-using-stored-procedures"></a>Настройка операций за счет хранимых процедур
Использование хранимых процедур является наиболее распространенным методом переопределения поведения по умолчанию. В примерах данного раздела показано, как можно использовать созданные оболочки методов для хранимых процедур и непосредственно вызывать хранимые процедуры.  
  
 При использовании Visual Studio можно использовать реляционный конструктор объектов для назначения хранимых процедур для выполнения операций вставки, обновления и удаления.  
  
> [!NOTE]
> Чтобы считать значения, созданные базой данных, используются выходные параметры хранимых процедур. Если вы не можете использовать выходные параметры, напишите частичную реализацию метода вместо того, чтобы полагаться на переопределения, созданные реляционный конструктор объектов. После успешного завершения операций `INSERT` или `UPDATE` необходимо установить соответствующие значения членов, сопоставленных значениям, созданным базой данных. Дополнительные сведения см. [в разделе обязанности разработчика при переопределении поведения по умолчанию](responsibilities-of-the-developer-in-overriding-default-behavior.md).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере предполагается, что класс `Northwind` содержит два метода для вызова хранимых процедур, используемых для переопределений в производном классе.  
  
### <a name="code"></a>Код  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Следующий класс использует эти методы для переопределения.  
  
### <a name="code"></a>Код  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Класс `NorthwindThroughSprocs` можно использовать точно так же, как класс `Northwnd`.  
  
### <a name="code"></a>Код  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Ответственность разработчика при переопределении поведения по умолчанию](responsibilities-of-the-developer-in-overriding-default-behavior.md)
