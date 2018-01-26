---
title: "Интерфейс ICLRStrongName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName
helpviewer_keywords: ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b8859cf507fb81f07b85b055380ba86aae471b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongname-interface"></a>Интерфейс ICLRStrongName
Предоставляет базовые глобальные статические функции для подписи сборки со строгими именами. Все `ICLRStrongName` методы возвращают стандартные результаты COM HRESULT.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)|Возвращает хэш файла указанную сборку, с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)|Возвращает хэш файла сборки, указанного как строка Юникода, с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)|Возвращает хэш сборки по указанному адресу памяти, с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)|Создает хэш содержимого указанного файла.|  
|[Метод GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)|Создает хэш содержимого файла, заданный строкой в Юникоде.|  
|[Метод GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)|Создает хэш содержимого файла с помощью заданного дескриптора файла, с помощью указанного хэш-алгоритма.|  
|[Метод StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)|Определяет, является ли две сборки отличаются только по их подписи строгого имени.|  
|[Метод StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Освобождает память, выделенная с предыдущим вызовом метода строгого имени, таких как [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), или [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[Метод StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)|Заполняет указанный буфер двоичное представление исполняемого файла по указанному адресу.|  
|[Метод StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)|Возвращает двоичное представление образа сборки по указанному адресу памяти.|  
|[Метод StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)|Возвращает открытый ключ из пары закрытого и открытого ключей.|  
|[Метод StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)|Возвращает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.|  
|[Метод StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)|Удаляет указанный контейнер ключей.|  
|[Метод StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)|Создает новую пару открытого и закрытого ключей для использования строгого имени.|  
|[Метод StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)|Создает новую пару открытого и закрытого ключей с указанным размером ключа для строгого имени использования.|  
|[Метод StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)|Импортирует пару открытого и закрытого ключей в контейнере.|  
|[Метод StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)|Создает подпись со строгим именем для указанной сборки.|  
|[Метод StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)|Создает подпись со строгим именем для указанной сборки, в зависимости от указанных флагов.|  
|[Метод StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)|Возвращает размер подписи строгого имени.|  
|[Метод StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)|Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени, которая будет проверена в соответствии с заданными флагами.|  
|[Метод StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)|Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.|  
|[Метод StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Проверяет допустимость сборки, который уже сопоставлен в памяти для связанного открытого ключа.|  
|[Метод StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)|Создает маркер строгого имени из указанного файла сборки.|  
|[Метод StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)|Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ.|  
|[Метод StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)|Возвращает токен, представляющий открытый ключ.|  
  
## <a name="remarks"></a>Примечания  
 Можно получить экземпляр `ICLRStrongName` путем вызова [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) с помощью метода `CLSID_CLRStrongName` и `IID_ICLRStrongName` в качестве параметров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
