---
title: Строгое именование (справочник по управляемым API)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45f3e8533bf7400566304ddb0fdd9d8e5a9b4280
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456134"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Строгое именование (справочник по управляемым API)
API строгого именования позволяет клиенту администрировать подписание сборок строгим именем.  
  
 При подписи сборки строгим именем в файл, содержащий манифест сборки, добавляется зашифрованный открытый ключ. Подпись строгим именем гарантирует уникальность имени, предотвращает подмену имени и после разрешения ссылки предоставляет уникальный идентификатор вызывающему объекту. Однако со строгим именем не связано никакого уровня доверия.  
  
## <a name="in-this-section"></a>В этом разделе  
  
> [!NOTE]
>  Все эти функции являются нерекомендуемыми начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Рекомендуемые альтернативы см. в интерфейсе [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md).  
  
 [Функция GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Получает хэш файла сборки, указанного строкой Юникода, с помощью указанного хэш-алгоритма. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromBlob](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Создает хэш содержимого указанного файла.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Создает хэш содержимого файла, указанного строкой Юникода. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromHandle](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Определяет, отличаются ли две сборки только подписями строгого имени. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Получает код последней ошибки, вызванной одной из функций строгого имени.  
  
 [Функция StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Освобождает память, выделенную предыдущим вызовом функции строгого имени, такой как [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) или [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameGetBlob](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Получает двоичное представление образа сборки по указанному адресу памяти. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Получает открытый ключ из пары закрытого и открытого ключей. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameHashSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Удаляет указанный контейнер ключей. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyGen](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Создает пару открытого и закрытого ключей для использования строгого имени.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Создает пару открытого и закрытого ключей с заданным размером для использования строгого имени. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Импортирует пару открытого и закрытого ключей в контейнер.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Создает подпись строгого имени для указанной сборки.   Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Создает подпись строгого имени для указанной сборки в зависимости от указанных флагов.    Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Возвращает размер подписи строгого имени. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Проверяет допустимость сборки, которая уже была сопоставлена с памятью, для связанного открытого ключа. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Создает маркер строгого имени из указанного файла сборки.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Получает маркер, представляющий открытый ключ. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Структура PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Представляет открытый ключ из пары открытого и закрытого ключей в двоичном формате.  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Справочник по неуправляемым API](../../../../docs/framework/unmanaged-api/index.md)
