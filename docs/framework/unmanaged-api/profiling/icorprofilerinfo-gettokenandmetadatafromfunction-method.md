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
ms.openlocfilehash: d924dbf21a0f0b046c8d8f8f294e91bc5ff6c015
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869415"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>Метод ICorProfilerInfo::GetTokenAndMetadataFromFunction
Возвращает маркер метаданных и экземпляр интерфейса метаданных, который может использоваться для токена указанной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор функции, для которой необходимо получить токен метаданных и интерфейс метаданных.  
  
 `riid`  
 окне Идентификатор ссылки интерфейса метаданных для получения экземпляра.  
  
 `ppImport`  
 заполняет Указатель на адрес экземпляра интерфейса метаданных, который может использоваться с токеном для указанной функции.  
  
 `pToken`  
 заполняет Указатель на маркер метаданных для указанной функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
