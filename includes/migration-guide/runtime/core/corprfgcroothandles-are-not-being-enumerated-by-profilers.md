---
ms.openlocfilehash: 8dc98b2d9c2c0b5f145ebce48cf8f5e054975c6e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858430"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a>Профилировщики не перечисляют COR_PRF_GC_ROOT_HANDLE

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5.1 API профилирования <code>RootReferences2()</code> по ошибке никогда не возвращает <code>COR_PRF_GC_ROOT_HANDLE</code> (вместо этого возвращается <code>COR_PRF_GC_ROOT_OTHER</code>). Эта проблема решена в .NET Framework 4.6.|
|Предложение|Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Версия|4.5.1|
|Тип|Среда выполнения|

