---
title: "Форматирование сообщений в службах рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d2367f4fe4ebe576eb9a5e2f707eb043e5ee7ccb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="formatting-messages-in-workflow-services"></a>Форматирование сообщений в службах рабочего процесса
В этом образце показано, как использовать различные пользовательские типы в действиях обмена сообщениями (в службах WF). Образец показывает простую службу утверждения затрат. Он представляет три операции. `ApproveExpense` принимает значение типа контракта данных и показывает, как использовать известные типы. Операция возвращает значение `true` или `false` в зависимости от суммы затрат. `ApprovePO`принимает значение типа XmlSerializer и возвращает `true` или `false` зависимости от суммы затрат.`ApprovedVendor` Получает тип контракта сообщения и возвращает `true` или `false` Если поставщик имеется в списке утвержденных поставщиков или если запрос прибыл из финансового отдела (финансовый отдел может использовать любого поставщика).  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.  
  
2.  Вначале запустите службу, созданную в каталоге [базовый каталог решений]\FormatterService\bin\debug\.  
  
3.  Затем запустите клиентское приложение, созданное в каталоге [базовый каталог решений]\FormatterClient\bin\debug.  
  
4.  Клиент вызывает три операции службы и печатает результаты. После завершения нажмите клавишу ВВОД, чтобы закрыть клиент и службу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`