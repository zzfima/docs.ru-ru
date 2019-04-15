---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234288"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>Исключение ObjectDisposedException, создаваемое средством проверки орфографии WPF

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях при завершении работы приложений WPF происходит сбой с исключением <xref:System.ObjectDisposedException?displayProperty=name>, создаваемым средством проверки орфографии. Эта ошибка исправлена в WPF .NET Framework 4.7 за счет правильной обработки этого исключения, что позволяет исключить подобное нежелательное поведение приложений. Следует отметить, что случайные первичные исключения могут по-прежнему наблюдаться в приложениях, выполняемых в режиме отладки.|
|Предложение|Выполните обновление до .NET Framework 4.7.|
|Область|Пограничный случай|
|Версия|4.6.1|
|Тип|Среда выполнения|
