---
title: "Хранимые процедуры CLR | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Хранимые процедуры CLR
Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях.  Они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.  
  
> [!NOTE]
>  Microsoft Visual Basic не поддерживает выходные параметры так, как это сделано в Microsoft Visual C\#.  Необходимо передать параметр по ссылке и применить атрибут \<Out\(\)\> для указания выходного параметра, как в следующем примере:  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1.  [Хранимые процедуры CLR](http://go.microsoft.com/fwlink/?LinkID=115400)  
  
## См. также  
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ru-ru/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)