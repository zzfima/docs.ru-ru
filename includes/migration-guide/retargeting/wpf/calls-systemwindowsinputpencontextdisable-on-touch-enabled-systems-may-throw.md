---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887830"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях вызовы внутреннего метода **System.Windows.Intput.PenContext.Disable** в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение <code>T:System.ArgumentException</code> из-за повторного входа.|
|Предложение|Эта проблема была устранена в .NET Framework 4.7. Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.|
|Область|Пограничный случай|
|Версия|4.6.1|
|Тип|Изменение целевой платформы|
