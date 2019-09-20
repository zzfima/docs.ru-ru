---
title: Функция StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48cdd550e5d8c7c75a603d74456e99a066d5c599
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798976"
---
# <a name="strongnamesignaturegeneration-function"></a>Функция StrongNameSignatureGeneration
Создает подпись строгого имени для указанной сборки.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к файлу, содержащему манифест сборки, для которой будет создана подпись строгого имени.  
  
 `wszKeyContainer`  
 окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.  
  
 Если `pbKeyBlob` параметр имеет значение `wszKeyContainer` null, необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.  
  
 Если `pbKeyBlob` значение не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).  
  
 Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA). В настоящее время не поддерживаются никакие другие типы ключей.  
  
 `pbKeyBlob`  
 окне Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданный функцией Win32 `CryptExportKey` . Если `pbKeyBlob` аргумент имеет значение null, предполагается, `wszKeyContainer` что контейнер ключей, заданный параметром, содержит пару ключей.  
  
 `cbKeyBlob`  
 окне Размер (в байтах `pbKeyBlob`).  
  
 `ppbSignatureBlob`  
 заполняет Указатель на расположение, в которое среда CLR возвращает подпись. Если `ppbSignatureBlob` параметр имеет значение null, среда выполнения сохраняет подпись в файле, указанном параметром `wszFilePath`.  
  
 Если `ppbSignatureBlob` значение не равно null, среда CLR выделяет пространство, в которое возвращается подпись. Вызывающий объект должен освободить это пространство с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbSignatureBlob`  
 заполняет Размер возвращенной сигнатуры в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае —. `false`  
  
## <a name="remarks"></a>Примечания  
 Укажите значение NULL `wszFilePath` для, чтобы вычислить размер подписи без создания подписи.  
  
 Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.  
  
 Если функция `StrongNameSignatureGeneration` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Метод StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
