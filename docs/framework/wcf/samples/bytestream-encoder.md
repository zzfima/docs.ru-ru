---
title: Кодировщик ByteStream
ms.date: 03/30/2017
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
ms.openlocfilehash: ab9ccf47527dcf7f01f272f09b3b341d30fbd8d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499684"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте файл ByteStreamHttpBinding.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Запустите новый экземпляр проекта ByteStreamHttpBindingServer, щелкнув правой кнопкой мыши проект в обозревателе решений и выбрав **отладки**, а затем **запустить новый экземпляр** в контекстном меню.  
  
3.  Запустите новый экземпляр проекта ByteStreamHttpBindingClient, щелкнув правой кнопкой мыши проект в обозревателе решений и выбрав **отладки**, **запустить новый экземпляр** в контекстном меню.
