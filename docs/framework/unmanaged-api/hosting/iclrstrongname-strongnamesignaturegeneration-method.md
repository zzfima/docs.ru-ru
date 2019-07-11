---
title: Метод ICLRStrongName::StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78a99132b1d4e0c61041bba3fe064c61c4722f19
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775683"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>Метод ICLRStrongName::StrongNameSignatureGeneration
Создает подпись строгого имени для указанной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameSignatureGeneration (   
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
 [in] Путь к файлу, содержащему манифест сборки, для которого требуется создать подпись строгого имени.  
  
 `wszKeyContainer`  
 [in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.  
  
 Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщик служб шифрования (CSP). В этом случае для подписывания файла используется пара ключей, хранящихся в контейнере.  
  
 Если `pbKeyBlob` не равно null, предполагается, что пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).  
  
 Ключи должны быть Rivest-Шамир-Adleman 1024-разрядный (RSA) ключи подписывания. Другие типы ключей не поддерживаются в настоящее время.  
  
 `pbKeyBlob`  
 [in] Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданные Win32 `CryptExportKey` функции. Если `pbKeyBlob` имеет значение null, контейнере ключей `wszKeyContainer` предполагается, что содержит пару ключей.  
  
 `cbKeyBlob`  
 [in] Размер в байтах из `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Указатель на расположение, к которому среда CLR возвращает подпись. Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, указанный параметром `wszFilePath`.  
  
 Если `ppbSignatureBlob` — не равно null, среда CLR выделяет место для возвращения подписи. Вызывающий объект должен освободить это пространство с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.  
  
 `pcbSignatureBlob`  
 [out] Размер в байтах, возвращаемой сигнатуры.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="remarks"></a>Примечания  
 Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.  
  
 Подписи могут быть сохранены либо непосредственно в файле или возвращается вызывающей стороне.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
