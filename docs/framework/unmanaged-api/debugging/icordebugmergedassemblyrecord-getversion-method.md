---
title: Метод ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 8b5995183be7f1c992cf3230e16456cb248eff0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793081"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>Метод ICorDebugMergedAssemblyRecord::GetVersion
Возвращает сведения о версии сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pMajor`  
 [out] Указатель на основной номер версии.  
  
 `pMinor`  
 [out] Указатель на дополнительный номер версии.  
  
 `pBuild`  
 [out] Указатель на номер сборки.  
  
 `pRevision`  
 [out] Указатель на номер редакции.  
  
## <a name="remarks"></a>Заметки  
 Сведения о версии сборки см в разделе, посвященном классу <xref:System.Version>.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
