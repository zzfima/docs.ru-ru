---
title: Метод ICorDebugSymbolProvider::GetMethodProps
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784fcb10e9c0c3c6ff50c25d47bb4fb3fd5762ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953287"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>Метод ICorDebugSymbolProvider::GetMethodProps
Возвращает сведения о свойствах метода, такие как токен метаданных метода и сведения о его универсальных параметрах, для указанного относительного виртуального адреса (RVA) в этом методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `codeRVA`  
 [in] Относительный виртуальный адрес в методе, сведения о котором требуется извлечь.  
  
 `pMethodToken`  
 [out] Указатель на токен метаданных метода.  
  
 `pcGenericParams`  
 [out] Указатель на количество универсальных параметров, связанных с данным методом.  
  
 `cbSignature`  
 [in] Размер массива `signature`. См. раздел примeчаний.  
  
 `pcbSignature`  
 [out] Указатель на размер возвращаемого массива `signature`.  
  
 `signature`  
 [out] Буфер, в котором хранятся сигнатуры TypeSpec для всех универсальных параметров.  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить требуемый размер метода `signature` массива, задайте `cbSignature` аргумент 0 и `signature` для **null**. После возврата метода параметр `pcbSignature` будет содержать число байт, требуемое для массива `signature`.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetTypeProps](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
