---
title: Хранимые процедуры CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 9b31d93c1ebc0af9aa8e41b3a4c328af62da7e23
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230815"
---
# <a name="clr-stored-procedures"></a>Хранимые процедуры CLR
Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях. Они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.  
  
> [!NOTE]
>  Microsoft Visual Basic не поддерживает выходные параметры так, как это сделано в Microsoft Visual C#. Необходимо указать, чтобы передать параметр по ссылке и применить \<Out() > атрибут для представления выходного параметра, как описано ниже:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Дополнительные сведения см. в разделе версии [документации по SQL Server](/sql) для версии SQL Server, вы используете.
  
 **Документация по SQL Server**

1. [Хранимые процедуры CLR](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>См. также

- [Создание объектов SQL Server 2005 в управляемом коде](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
