---
title: Метод ICLRStrongName::StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
ms.openlocfilehash: 34614fe24127787a113bab4975a50f1c8d2d875e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899500"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a>Метод ICLRStrongName::StrongNameSignatureGenerationEx
Создает подпись строгого имени для указанной сборки в соответствии с заданными флагами.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к файлу, содержащему манифест сборки, для которой будет создана подпись строгого имени.  
  
 `wszKeyContainer`  
 окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.  
  
 Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.  
  
 Если `pbKeyBlob` не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).  
  
 `pbKeyBlob`  
 окне Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданный функцией Win32 `CryptExportKey`. Если `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром `wszKeyContainer`, содержит пару ключей.  
  
 `cbKeyBlob`  
 окне Размер `pbKeyBlob`в байтах.  
  
 `ppbSignatureBlob`  
 заполняет Указатель на расположение, в которое среда CLR возвращает подпись. Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файле, указанном `wszFilePath`.  
  
 Если `ppbSignatureBlob` не равно null, среда CLR выделяет пространство, в которое возвращается подпись. Вызывающий объект должен освободить это пространство с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbSignatureBlob`  
 заполняет Размер возвращенной сигнатуры в байтах.  
  
 `dwFlags`  
 окне Одно или несколько из следующих значений:  
  
- `SN_SIGN_ALL_FILES` (0x00000001) — повторное вычисление всех хэшей для связанных модулей.  
  
- `SN_TEST_SIGN` (0x00000002) — Тестовая подпись сборки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Заметки  
 Укажите значение NULL для `wszFilePath`, чтобы вычислить размер подписи без создания подписи.  
  
 Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.  
  
 Если `SN_SIGN_ALL_FILES` указан, но открытый ключ не включен (как `pbKeyBlob`, так и `wszFilePath` равны NULL), хэши для связанных модулей пересчитываются, но сборка не подписывается повторно.  
  
 Если указан параметр `SN_TEST_SIGN`, заголовок среды CLR не изменяется, указывая, что сборка подписана строгим именем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
