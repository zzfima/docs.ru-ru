---
title: "Кодировщик ByteStream"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0984d3989d6441c363730454ea65b0393c94b9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="bytestream-encoder"></a>Кодировщик ByteStream
В этом образце показано, как создать привязку `ByteStreamHttpBinding`, которая имеет тип <xref:System.ServiceModel.Channels.Binding> и демонстрирует функциональные возможности кодировщика байтового потока.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано, как создать стандартную привязку <xref:System.ServiceModel.Channels.Binding> с использованием стандартных элементов привязки <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> и <xref:System.ServiceModel.Channels.HttpTransportBindingElement>. В этом образце показано, как использовать кодировщик байтового потока для передачи и загрузки изображения. Функция кодировщика байтового потока поддерживает только транспорт HTTP и не поддерживает такие функции, как надежный обмен сообщениями и безопасность. Для <xref:System.ServiceModel.Channels.MessageVersion> поддерживается только значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
> [!IMPORTANT]
>  Если этот образец работает в [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] или [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], убедитесь, что среда [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] запущена с повышенными привилегиями.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте файл ByteStreamHttpBinding.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Запустите новый экземпляр проекта ByteStreamHttpBindingServer, щелкнув правой кнопкой мыши проект в обозревателе решений и выбрав **отладки**, а затем **запустить новый экземпляр** в контекстном меню.  
  
3.  Запустите новый экземпляр проекта ByteStreamHttpBindingClient, щелкнув правой кнопкой мыши проект в обозревателе решений и выбрав **отладки**, **запустить новый экземпляр** в контекстном меню.
