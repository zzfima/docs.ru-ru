---
title: Калькулятор с корреляцией
ms.date: 03/30/2017
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
ms.openlocfilehash: 71cfdd0906ef20ec36b76ef5e508a4551b9fe3fe
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384675"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`