---
title: Трассировка сети в .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework], network tracing
- methods, network tracing
- Networking
- trace enabled debugging
- network tracing, about network tracing
- network tracing
- network, network tracing
- traffic tracing
- tracing [.NET Framework], network
- deploying applications [.NET Framework], network traffic
- capturing network traffic
- Internet, network tracing
- Network Resources
- output, network tracing
- method invocations
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 505c5f39890f7f362c5f5d8525a65f8c3d05624a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398044"
---
# <a name="network-tracing-in-the-net-framework"></a>Трассировка сети в .NET Framework
Трассировка сети в .NET Framework предоставляет доступ к сведениям о вызовах методов и о сетевом трафике, созданном управляемым приложением. Эта возможность полезна для отладки приложений на стадии разработки, а также для анализа развернутых приложений. Выходные данные трассировки сети можно настраивать с целью поддержки различных сценариев использования во время разработки и в производственной среде.  
  
 Чтобы включить трассировку сети в .NET Framework, необходимо выбрать назначение для выходных данных трассировки и добавить параметры конфигурации трассировки сети в файл конфигурации приложения или компьютера. Описание файлов конфигурации и их использования см. в разделе [Файлы конфигурации](../../../docs/framework/configure-apps/index.md). Сведения о том, как включить трассировку сети, см. в разделе [Включение трассировки сети](../../../docs/framework/network-programming/enabling-network-tracing.md). Сведения о параметрах, которые необходимо добавить в файл конфигурации, см. в разделе [Практическое руководство. Настройка трассировки сети](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
 Если трассировка включена, сведения о трассировке можно получать с помощью классов **System.Net**. Члены класса сети, которые формируют данные трассировки, содержат следующее примечание в разделе комментариев в документации по библиотеке классов .NET Framework:  
  
> [!NOTE]
>  Данный член генерирует сведения трассировки, если в приложении включена трассировка сети. Дополнительные сведения о трассировке см. в разделе "Трассировка сети".  
  
## <a name="see-also"></a>См. также  
 [Включение трассировки сети](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [Практическое руководство. Настройка трассировки сети](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)  
 [Интерпретация трассировки сети](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [Введение. Подготовка к инструментированию и трассировка](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
