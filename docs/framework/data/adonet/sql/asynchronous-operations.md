---
title: "Асинхронные операции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d32c3c-bf78-4bfc-a357-c9e82e4a4b3c
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6f631d785698ae59370053c4e35307514c44087c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="asynchronous-operations"></a>Асинхронные операции
Для завершения некоторых операций базы данных, например для выполнения команд, требуется значительное время. В таком случае однопотоковые приложения должны блокировать другие операции и ждать окончания команды перед тем, как они смогут продолжить свои собственные операции. В противоположность этому, так как поток переднего плана может назначать долговременные операции фоновому потоку, он остается активным во время всей операции. Приложение Windows, например, делегирующее долговременную операцию фоновому потоку, позволяет потоку пользовательского интерфейса реагировать при выполнении операции.  
  
 .NET Framework предоставляет несколько асинхронных шаблонов конструирования, которые разработчики могут использовать для извлечения преимуществ из фоновых потоков и освобождает пользовательский интерфейс высокоприоритетных потоков от выполнения других операций. ADO.NET поддерживает те же шаблоны конструирования в его классе <xref:System.Data.SqlClient.SqlCommand>. Конкретнее, методы <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A> и <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> в сочетании с методами <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> и <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A> предоставляют асинхронную поддержку.  
  
> [!NOTE]
>  Асинхронное программирование является основной возможностью .NET Framework, а ADO.NET пользуется всеми преимуществами стандартных шаблонов конструирования. Дополнительные сведения о разных асинхронных методов, доступных разработчикам см. в разделе [асинхронный вызов синхронных методов](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
 Хотя использование асинхронной техники при помощи возможностей ADO.NET не требует какого-либо дополнительного специального рассмотрения, имеется большая вероятность того, что большинство разработчиков будет использовать асинхронные возможности в ADO.NET, а не в других областях .NET Framework. Важно знать о преимуществах и проблемах создания многопотоковых приложений. Приводимые далее в этом разделы примеры указывают на несколько важных проблем, которые должны учитывать разработчики при построении приложений, включающих функциональные возможности многопотоковой техники.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Приложения Windows, использующие обратные вызовы](../../../../../docs/framework/data/adonet/sql/windows-applications-using-callbacks.md)  
 Предоставляет пример, демонстрирующий, как безопасно выполнить асинхронную команду, правильно обрабатывающую взаимодействие с формой и свое содержимое из отдельного потока.  
  
 [Приложения ASP.NET, использующие дескрипторы ожидания](../../../../../docs/framework/data/adonet/sql/aspnet-apps-using-wait-handles.md)  
 Предоставляет пример, демонстрирующий, как выполнить несколько параллельных команд из страницы ASP.NET, используя обработки ожидания для управления операцией по завершении всех команд.  
  
 [Выполнение опросов в консольных приложениях](../../../../../docs/framework/data/adonet/sql/polling-in-console-applications.md)  
 Предоставляет пример, демонстрирующий использование ждущего режима для ожидания завершения выполнения асинхронной команды из приложения командной строки. Эта техника также действительна в библиотеке классов или в другом приложении без пользовательского интерфейса.  
  
## <a name="see-also"></a>См. также  
 [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Асинхронный вызов синхронных методов](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
