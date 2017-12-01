---
title: "Калькулятор с корреляцией"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 53d96e090edabc65b7356497c3726d29e46c4ea7
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="correlated-calculator"></a>Калькулятор с корреляцией
В этом образце демонстрируется, как действия по обмену сообщениями (<xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>) могут использоваться в конструкторе с корреляцией на основе содержимого в зависимости от параметра в сообщении. В этом сценарии операции калькулятора находятся в параллельном сопровождении. Экземпляр и корреляция (на основе `CalculatorId`) создаются после отправки первого сообщения в рабочий процесс, и последующие сообщения с тем же `CalculatorId` отправляются на тот же экземпляр до вызова операции сброса. Клиент реализуется в виде приложения WPF, использующего основанный на коде прокси-агент клиента для взаимодействия со службой.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, откройте файл решения For.sln.  
  
    1.  Перейдите в папку, содержащую [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Щелкните правой кнопкой Devenv.exe и выберите **Запуск от имени администратора**.  
  
2.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения CorrelatedCalculator.sln.  
  
3.  Для построения решения нажмите CTRL+SHIFT+B.  
  
4.  Нажмите клавиши Ctrl + F5, чтобы запустить проект службы.  
  
5.  После того как служба готова к прослушиванию сообщений, щелкните правой кнопкой мыши проект «Клиент» в обозревателе решений и запустите его.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`