---
title: Функция StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798985"
---
# <a name="strongnamesignaturegenerationex-function"></a>Функция StrongNameSignatureGenerationEx
Создает подпись строгого имени для указанной сборки в соответствии с заданными флагами.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
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
  
 Если `pbKeyBlob` параметр имеет значение `wszKeyContainer` null, необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.  
  
 Если `pbKeyBlob` значение не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).  
  
 `pbKeyBlob`  
 окне Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданный функцией Win32 `CryptExportKey` . Если `pbKeyBlob` аргумент имеет значение null, предполагается, `wszKeyContainer` что контейнер ключей, заданный параметром, содержит пару ключей.  
  
 `cbKeyBlob`  
 окне Размер (в байтах `pbKeyBlob`).  
  
 `ppbSignatureBlob`  
 заполняет Указатель на расположение, в которое среда CLR возвращает подпись. Если `ppbSignatureBlob` параметр имеет значение null, среда выполнения сохраняет подпись в файле, указанном параметром `wszFilePath`.  
  
 Если `ppbSignatureBlob` значение не равно null, среда CLR выделяет пространство, в которое возвращается подпись. Вызывающий объект должен освободить это пространство с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbSignatureBlob`  
 заполняет Размер возвращенной сигнатуры в байтах.  
  
 `dwFlags`  
 окне Одно или несколько из следующих значений:  
  
- `SN_SIGN_ALL_FILES`(0x00000001) — повторное вычисление всех хэшей для связанных модулей.  
  
- `SN_TEST_SIGN`(0x00000002) — Тестовая подпись сборки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае —. `false`  
  
## <a name="remarks"></a>Примечания  
 Укажите значение NULL `wszFilePath` для, чтобы вычислить размер подписи без создания подписи.  
  
 Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.  
  
 Если `SN_SIGN_ALL_FILES` указан параметр, но открытый ключ не включен `pbKeyBlob` (и `wszFilePath` имеет значение null), хэши для связанных модулей пересчитываются, но сборка не подписывается повторно.  
  
 Если `SN_TEST_SIGN` указан параметр, заголовок среды CLR не изменяется, чтобы указать, что сборка подписана строгим именем.  
  
 Если функция `StrongNameSignatureGenerationEx` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Метод StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
