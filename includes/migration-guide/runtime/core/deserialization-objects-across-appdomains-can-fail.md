---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804891"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Десериализация объектов между доменами приложений может завершиться сбоем

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.|
|Предложение|См. статью [Устранение рисков: десериализация объектов между доменами приложений](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)|
|Область|Пограничный случай|
|Версия|4.5.1|
|Тип|Среда выполнения|
