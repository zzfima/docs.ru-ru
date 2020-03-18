---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858430"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>Профилировщики не перечисляют COR_PRF_GC_ROOT_HANDLE

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.5.1 API профилирования <code>RootReferences2()</code> по ошибке никогда не возвращает <code>COR_PRF_GC_ROOT_HANDLE</code> (вместо этого возвращается <code>COR_PRF_GC_ROOT_OTHER</code>). Эта проблема решена в .NET Framework 4.6.|
|Предложение|Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Version|4.5.1|
|Type|Параметры выполнения|
