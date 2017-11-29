---
title: "Функция StrongNameSignatureGenerationEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureGenerationEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureGenerationEx
helpviewer_keywords: StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49000a00f278b4c1dd7a2eeded7eb91a592c863f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturegenerationex-function"></a>Функция StrongNameSignatureGenerationEx
Создает подпись со строгим именем для указанной сборки в соответствии с заданными флагами.  
  
 Эта функция устарела. Используйте [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) метод вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Путь к файлу, содержащему манифест сборки, для которого будет создаваться подписи строгого имени.  
  
 `wszKeyContainer`  
 [in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.  
  
 Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае для подписания файла используется пара ключей, хранящихся в контейнере.  
  
 Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).  
  
 `pbKeyBlob`  
 [in] Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданные Win32 `CryptExportKey` функции. Если `pbKeyBlob` равен null, контейнер ключей, заданные `wszKeyContainer` должна содержать пары ключей.  
  
 `cbKeyBlob`  
 [in] Размер в байтах для `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Указатель на расположение, к которому Общеязыковая среда выполнения возвращает подпись. Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, заданный параметром `wszFilePath`.  
  
 Если `ppbSignatureBlob` — не null, общеязыковая среда выполнения выделяет место для возвращения подписи. Вызывающий объект должен освободить это место с помощью [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции.  
  
 `pcbSignatureBlob`  
 [out] Размер в байтах, возвращаемой подписи.  
  
 `dwFlags`  
 [in] Один или несколько из следующих значений:  
  
-   `SN_SIGN_ALL_FILES`(0x00000001) — повторно вычисляет все хэши для связанных модулей.  
  
-   `SN_TEST_SIGN`(0x00000002) — пробное подписание сборки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.  
  
 Подпись может быть либо хранятся непосредственно в файле или возвращается вызывающему.  
  
 Если `SN_SIGN_ALL_FILES` указан, но открытый ключ не был включен (оба `pbKeyBlob` и `wszFilePath` имеют значение null), заново вычисляются хэши для связанных модулей, но сборка не подписана заново.  
  
 Если `SN_TEST_SIGN` указан, заголовок среды CLR не изменяется для указания, что сборка подписана строгим именем.  
  
 Если `StrongNameSignatureGenerationEx` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [Метод StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [Iclrstrongname-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
