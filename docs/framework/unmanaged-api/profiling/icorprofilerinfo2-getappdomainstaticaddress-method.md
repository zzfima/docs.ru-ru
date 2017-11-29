---
title: "Метод ICorProfilerInfo2::GetAppDomainStaticAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetAppDomainStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type: apiref
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf82d20085137e8ac55cf864a21260222fd6b514
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>Метод ICorProfilerInfo2::GetAppDomainStaticAddress
Получает адрес поля статического домена указанное приложение, которое находится в области указанного домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентификатор класса для класса, содержащего поля статического домена запрошенное приложение.  
  
 `fieldToken`  
 [in] Токен метаданных для запрошенного приложения статического поля домена.  
  
 `appDomainId`  
 [in] Идентификатор домена приложения, который является областью для запрошенного статического поля.  
  
 `ppAddress`  
 [out] Указатель на адрес статического поля в пределах указанного домена приложения.  
  
## <a name="remarks"></a>Примечания  
 `GetAppDomainStaticAddress` Метод может возвращать одно из следующих действий:  
  
-   CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.  
  
-   Адреса объектов, которые могут находиться в куче сборщика мусора. Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора профилировщики не следует предполагать, что они являются допустимыми.  
  
 До завершения конструктора класса `GetAppDomainStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
