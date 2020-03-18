---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887830"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException

|   |   |
|---|---|
|Подробнее|В некоторых случаях вызовы внутреннего метода **System.Windows.Intput.PenContext.Disable** в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение <code>T:System.ArgumentException</code> из-за повторного входа.|
|Предложение|Эта проблема была устранена в .NET Framework 4.7. Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.|
|Область|Пограничный случай|
|Version|4.6.1|
|Type|Изменение целевой платформы|
