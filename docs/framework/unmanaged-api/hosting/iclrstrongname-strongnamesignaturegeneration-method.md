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
ms.openlocfilehash: 217b54a615d7c553e714ef87b3c2bb6a1919ae98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>Метод ICLRStrongName::StrongNameSignatureGeneration
Создает подпись со строгим именем для указанной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Путь к файлу, содержащему манифест сборки, для которого будет создаваться подписи строгого имени.  
  
 `wszKeyContainer`  
 [in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.  
  
 Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае для подписания файла используется пара ключей, хранящихся в контейнере.  
  
 Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).  
  
 Ключи должны быть 1024-разрядный Rivest шифрования RSA--Adleman () ключей подписывания. Другие типы ключей не поддерживаются в данный момент.  
  
 `pbKeyBlob`  
 [in] Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданные Win32 `CryptExportKey` функции. Если `pbKeyBlob` равен null, контейнер ключей, заданные `wszKeyContainer` должна содержать пары ключей.  
  
 `cbKeyBlob`  
 [in] Размер в байтах для `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Указатель на расположение, к которому Общеязыковая среда выполнения возвращает подпись. Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, заданный параметром `wszFilePath`.  
  
 Если `ppbSignatureBlob` — не null, общеязыковая среда выполнения выделяет место для возвращения подписи. Вызывающий объект должен освободить это пространство с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.  
  
 `pcbSignatureBlob`  
 [out] Размер в байтах, возвращаемой подписи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).  
  
## <a name="remarks"></a>Примечания  
 Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.  
  
 Подпись может быть храниться непосредственно в файле или возвращается вызывающему.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
