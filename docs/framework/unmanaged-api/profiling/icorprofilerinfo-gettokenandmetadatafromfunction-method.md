---
title: Метод ICorProfilerInfo::GetTokenAndMetadataFromFunction
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e7f2e8247d3ba822cc09a98f985926e6b5400c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206893"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>Метод ICorProfilerInfo::GetTokenAndMetadataFromFunction
Получает маркер метаданных и экземпляр интерфейса метаданных, который может использоваться в отношении маркера для указанной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, для которого необходимо получить токен метаданных и интерфейс метаданных.  
  
 `riid`  
 [in] Идентификатор ссылки на интерфейс метаданных для получения экземпляра.  
  
 `ppImport`  
 [out] Указатель на адрес экземпляр интерфейса метаданных, который может использоваться в отношении маркера для указанной функции.  
  
 `pToken`  
 [out] Указатель на токен метаданных для указанной функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
