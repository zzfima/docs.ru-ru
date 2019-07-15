---
ms.openlocfilehash: 107b34c7bd26e1396e8a6638d6929c15de92b8e4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803180"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>Профилирование приложений ASP.Net MVC4 может привести к неустранимой ошибке подсистемы выполнения

|   |   |
|---|---|
|Подробные сведения|Профилирование с использованием сборок NGEN /Profile может привести к сбою при запуске профилируемых приложений ASP.NET MVC4 с неустранимой ошибкой подсистемы выполнения|
|Предложение|Эта проблема решена в .NET Framework 4.5.2. Также можно избежать этой проблемы, указав <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> в маске события профилировщика.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|

