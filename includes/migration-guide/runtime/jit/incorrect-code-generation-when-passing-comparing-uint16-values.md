---
ms.openlocfilehash: b23909c53b451b4b18bf0ccdf59f51e7c8e3114f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761460"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Некорректное формирование кода при передаче и сравнении значений UInt16

|   |   |
|---|---|
|Подробные сведения|Из-за изменений, представленных в версии .NET Framework 4.7, в некоторых случаях созданный JIT-компилятором код в приложениях на платформе .NET Framework 4.7 некорректно сравнивает значения <code>T:System.UInt16</code>. Дополнительные сведения см. в разделе [Issue #11508: Silent bad codegen when passing and comparing ushort args](https://github.com/dotnet/coreclr/issues/11508) (Проблема № 11508. Некорректное автоматическое формирование кода при передаче и сравнении аргументов ushort) на веб-сайте GitHub.com.|
|Предложение|Если вы сталкиваетесь с проблемами при сравнении 16-разрядных значений без знака в .NET Framework 4.7, выполните обновление до .NET Framework 4.7.1.|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Среда выполнения|

