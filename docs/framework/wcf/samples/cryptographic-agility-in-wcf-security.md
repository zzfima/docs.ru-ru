---
title: Гибкость шифрования в безопасности WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714926"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Гибкость шифрования в безопасности WCF

В этом примере показано, как указать в стандартном или пользовательском алгоритме, чтобы обеспечить динамическую реализацию в клиенте Windows Communication Foundation (WCF) и службе. Образец состоит из следующих проектов.

**Service**

Это автономная служба WCF, которая реализует интерфейс `ICalculator` и защищает конечную точку с помощью <xref:System.ServiceModel.WSHttpBinding> с защищенным сеансом и отключением надежного сеанса. Служба определяет пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.

**Клиент**

Это клиент WCF, который обращается к службе после успешной проверки подлинности. Он вызывает операции, предоставляемые интерфейсом `ICalculator` и реализуемые службой. Клиент также определяет тот же пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.

## <a name="to-use-this-sample"></a>Использование этого образца

1. Откройте решение Криптоагилити. sln в Visual Studio 2012.

2. Чтобы построить решение, нажмите CTRL+SHIFT+B.

3. Откройте проводник и перейдите в каталог \Вкф\басик\секурити\криптоагилити\сервице\бин и запустите файл Service. exe с правами администратора, щелкнув правой кнопкой мыши Service. exe и выбрав **Запуск от имени администратора**.

4. Перейдите в каталог \WCF\Basic\Security\CryptoAgility\Client\bin и запустите файл client.exe обычным образом.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>См. также:

- [Безопасность Windows Communication Foundation](../feature-details/security.md)
