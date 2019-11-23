---
title: Практическое руководство. Использование пользовательских скалярных функций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: dfe82fd50eb3eedeaff9082a4288901f72197795
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003239"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Практическое руководство. Использование пользовательских скалярных функций
Для сопоставления клиентского метода, определенного в классе, с пользовательской функцией используется атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>. Обратите внимание, что тело метода создает выражение, перехватывающее назначение вызова метода, и передает это выражение в <xref:System.Data.Linq.DataContext> для преобразования и выполнения.  
  
> [!NOTE]
> Прямое выполнение возможно только при вызове функции вне запроса. Дополнительные сведения см. [в разделе инструкции. Вызов определяемых пользователем функций в встроенном](how-to-call-user-defined-functions-inline.md)виде.  
  
## <a name="example"></a>Пример  
 В следующем коде SQL представлена скалярная пользовательская функция `ReverseCustName()`.  
  
```sql  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 Для этого кода следует отобразить клиентский метод, подобный следующему.  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>См. также:

- [Определяемые пользователем функции](user-defined-functions.md)
