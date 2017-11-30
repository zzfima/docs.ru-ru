---
title: "Сбои при отправке и обработке"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 57d522918d280c9a8a68fcd420b7216cc48216d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="sending-and-handling-faults"></a>Сбои при отправке и обработке
В этом образце демонстрируется использование действий обмена сообщениями <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply> для отправки и получения сообщений об ожидаемых и непредвиденных ошибках. В этом сценарии первый запрос клиента дает в результате ожидаемую ошибку, которая была включена в коллекцию <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>. Следующие несколько запросов клиентов приводят к получению непредвиденных ошибок, после чего последний запрос дает положительный результат.  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.  
  
2.  Откройте файл решения Faults.sln.  
  
3.  Для построения решения нажмите CTRL+SHIFT+B.  
  
4.  Запустите проект службы.  
  
    1.  В **обозревателе решений**, щелкните правой кнопкой мыши `FaultService` проект и выберите **Назначить запускаемым проектом**.  
  
    2.  Нажмите клавиши CTRL+F5.  
  
5.  Откройте другую копию [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.  
  
6.  Откройте файл решения Faults.sln.  
  
7.  Запустите клиентский проект.  
  
    1.  В **обозревателе решений**, щелкните правой кнопкой мыши `FaultClient` проект и выберите **Назначить запускаемым проектом**.  
  
    2.  Нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`  
  
## <a name="see-also"></a>См. также
