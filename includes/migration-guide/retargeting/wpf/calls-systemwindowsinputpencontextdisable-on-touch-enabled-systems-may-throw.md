---
ms.openlocfilehash: 0778285ef1b5702bd79743038a1bd21ba04612d6
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804328"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях вызовы внутреннего метода <strong>System.Windows.Intput.PenContext.Disable</strong> в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение <code>T:System.ArgumentException</code> из-за повторного входа.|
|Предложение|Эта проблема была устранена в .NET Framework 4.7. Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.|
|Область|Пограничный случай|
|Версия|4.6.1|
|Тип|Изменение целевой платформы|

