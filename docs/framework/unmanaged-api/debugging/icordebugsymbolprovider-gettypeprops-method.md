---
title: "Метод ICorDebugSymbolProvider::GetTypeProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 118ae3991ea19b3158f4787a9944c28fb8208cbb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a>Метод ICorDebugSymbolProvider::GetTypeProps
Возвращает сведения о свойствах типа, такие как число сигнатур его универсальных параметров, исходя из относительного виртуального адреса (RVA) в таблице VTable.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tableRva`  
 [in] Относительный виртуальный адрес (RVA) в VTable.  
  
 `cbSignature`  
 [in] Размер массива `signature`. См. раздел примeчаний.  
  
 `pcbSignature`  
 [out] Указатель на размер возвращаемого массива `signature`.  
  
 `signature`  
 [out] Буфер, в котором хранятся сигнатуры TypeSpec для всех универсальных параметров.  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить требуемый размер типа `signature` массива, задайте `cbSignature` аргумент 0 и `signature` для **null**. После возврата метода параметр `pcbSignature` будет содержать число байт, требуемое для массива `signature`.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод GetMethodProps](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)  
 [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
