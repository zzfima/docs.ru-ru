---
title: Интерфейс ICLRStrongName
ms.date: 03/30/2017
api_name:
- ICLRStrongName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName
helpviewer_keywords:
- ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type:
- apiref
ms.openlocfilehash: 4f774915cdbb12b13fa334db37c8e0fa2a7e5829
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135132"
---
# <a name="iclrstrongname-interface"></a>Интерфейс ICLRStrongName
Предоставляет базовые глобальные статические функции для подписи сборок со строгими именами. Все методы `ICLRStrongName` возвращают стандартные значения HRESULT COM.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)|Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)|Получает хэш файла сборки, указанного строкой Юникода, с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)|Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)|Создает хэш содержимого указанного файла.|  
|[Метод GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)|Создает хэш содержимого файла, указанного строкой Юникода.|  
|[Метод GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)|Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.|  
|[Метод StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)|Определяет, отличаются ли две сборки только подписями строгого имени.|  
|[Метод StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Освобождает память, выделенную с помощью предыдущего вызова метода строгого имени, такого как [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)или [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[Метод StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)|Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.|  
|[Метод StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)|Получает двоичное представление образа сборки по указанному адресу памяти.|  
|[Метод StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)|Получает открытый ключ из пары закрытого и открытого ключей.|  
|[Метод StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)|Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.|  
|[Метод StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)|Удаляет указанный контейнер ключей.|  
|[Метод StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)|Создает пару открытого и закрытого ключей для использования строгого имени.|  
|[Метод StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)|Создает пару открытого и закрытого ключей с заданным размером для использования строгого имени.|  
|[Метод StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)|Импортирует пару открытого и закрытого ключей в контейнер.|  
|[Метод StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)|Создает подпись строгого имени для указанной сборки.|  
|[Метод StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)|Создает подпись строгого имени для указанной сборки в зависимости от указанных флагов.|  
|[Метод StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)|Возвращает размер подписи строгого имени.|  
|[Метод StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)|Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами.|  
|[Метод StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)|Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.|  
|[Метод StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Проверяет допустимость сборки, которая уже была сопоставлена с памятью, для связанного открытого ключа.|  
|[Метод StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)|Создает маркер строгого имени из указанного файла сборки.|  
|[Метод StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)|Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ.|  
|[Метод StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)|Получает маркер, представляющий открытый ключ.|  
  
## <a name="remarks"></a>Заметки  
 Экземпляр `ICLRStrongName` можно получить, вызвав метод [ICLRRuntimeInfo::](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) WebMethod, используя `CLSID_CLRStrongName` и `IID_ICLRStrongName` в качестве параметров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
