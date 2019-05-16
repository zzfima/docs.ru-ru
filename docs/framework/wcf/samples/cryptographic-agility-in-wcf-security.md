---
title: Криптографическая гибкость в системе безопасности WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 0a4171d6e753be9fbdd6974850fc6757ff585ae0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637827"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Криптографическая гибкость в системе безопасности WCF

В этом примере показано, как указать в стандартный или пользовательский алгоритм для быстрого внедрения криптографических функций в Windows Communication Foundation (WCF) клиент и служба. Образец состоит из следующих проектов.

**Service**

Это резидентной службы WCF, который реализует `ICalculator` интерфейс, а также обеспечивает защиту конечной точки с помощью <xref:System.ServiceModel.WSHttpBinding> с безопасного сеанса и надежного сеанса отключены. Служба определяет пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.

**Клиент**

Это клиента WCF, который обращается к службе после успешной проверки подлинности. Он вызывает операции, предоставляемые интерфейсом `ICalculator` и реализуемые службой. Клиент также определяет тот же пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.

## <a name="to-use-this-sample"></a>Использование этого образца

1. Откройте решение CryptoAgility.sln в Visual Studio 2012.

2. Чтобы построить решение, нажмите CTRL+SHIFT+B.

3. Откройте [!INCLUDE[fileExplorer](~/includes/fileexplorer-md.md)] и перейдите в каталог \WCF\Basic\Security\CryptoAgility\Service\bin и запустите файл service.exe с правами администратора, щелкнув правой кнопкой мыши service.exe и выбрав **Запуск от имени администратора**.

4. Перейдите в каталог \WCF\Basic\Security\CryptoAgility\Client\bin и запустите файл client.exe обычным образом.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>См. также

- [Windows Communication Foundation Security](../feature-details/security.md)
