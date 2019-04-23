---
ms.openlocfilehash: ad624a665dbe8e989ea05acc20213809e515e6ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804935"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Некорректное формирование кода при передаче и сравнении значений UInt16

|   |   |
|---|---|
|Подробные сведения|Из-за изменений, представленных в версии .NET Framework 4.7, в некоторых случаях созданный JIT-компилятором код в приложениях на платформе .NET Framework 4.7 некорректно сравнивает значения <code>T:System.UInt16</code>. Дополнительные сведения см. в разделе [Issue #11508: Silent bad codegen when passing and comparing ushort args](https://github.com/dotnet/coreclr/issues/11508) (Проблема № 11508. Некорректное автоматическое формирование кода при передаче и сравнении аргументов ushort) на веб-сайте GitHub.com.|
|Предложение|Если вы сталкиваетесь с проблемами при сравнении 16-разрядных значений без знака в .NET Framework 4.7, выполните обновление до .NET Framework 4.7.1.|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Среда выполнения|
