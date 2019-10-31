---
title: 'Метод метод icordebugsymbolprovider:: Жетмесодпропс'
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: 811106216e1e454ddf342af1578f74c80ba2acc9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138831"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>Метод метод icordebugsymbolprovider:: Жетмесодпропс
Возвращает сведения о свойствах метода, такие как токен метаданных метода и сведения о его универсальных параметрах, для указанного относительного виртуального адреса (RVA) в этом методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="remarks"></a>Заметки  
 Чтобы получить необходимый размер массива `signature` метода, присвойте аргументу `cbSignature` значение 0 и `signature` **значение NULL**. После возврата метода параметр `pcbSignature` будет содержать число байт, требуемое для массива `signature`.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetTypeProps](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
