---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235461"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Десериализация объектов между доменами приложений может завершиться сбоем

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.|
|Предложение|См. статью [Устранение рисков: десериализация объектов между доменами приложений](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)|
|Область|Пограничный случай|
|Версия|4.5.1|
|Тип|Среда выполнения|
