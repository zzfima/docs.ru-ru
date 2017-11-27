---
title: "Строгое именование (справочник по управляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86d741a16a0293892d0d6d90f1763d744ed3675d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strong-naming-unmanaged-api-reference"></a>Строгое именование (справочник по управляемым API)
API со строгим именованием позволяет клиенту администрировать подписание сборки строгим именем.  
  
 При подписи сборки строгим именем в файл, содержащий манифест сборки, добавляется зашифрованный открытый ключ. Подпись строгим именем гарантирует уникальность имени, предотвращает подмену имени и после разрешения ссылки предоставляет вызывающим уникальный идентификатор. Тем не менее уровень доверия не связан со строгим именем.  
  
## <a name="in-this-section"></a>Содержание  
 [Строгое именование глобальные статические функции](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 Описываются неуправляемые глобальные статические функции, которые использует API строгого именования.  
  
> [!NOTE]
>  Все эти функции являются устаревшими начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Рекомендуемые альтернативы. в разделе [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) интерфейса.  
  
 [Функция GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Возвращает хэш файла указанную сборку, с помощью указанного хэш-алгоритма. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Возвращает хэш файла сборки, указанного как строка Юникода, с помощью указанного хэш-алгоритма. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция GetHashFromBlob](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Возвращает хэш сборки по указанному адресу памяти, с помощью указанного хэш-алгоритма. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Создает хэш содержимого указанного файла.  Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Создает хэш содержимого файла, заданный строкой в Юникоде. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция GetHashFromHandle](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Создает хэш содержимого файла с помощью заданного дескриптора файла, с помощью указанного хэш-алгоритма.  Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Определяет, является ли две сборки отличаются только по их подписи строгого имени. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Возвращает последний код ошибки, вызванной одной из функций строгого имени.  
  
 [Функция StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Освобождает память, выделенная с предыдущим вызовом функции строгое имя, например [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), или [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameGetBlob](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Заполняет указанный буфер двоичное представление исполняемого файла по указанному адресу. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Возвращает двоичное представление образа сборки по указанному адресу памяти. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Возвращает открытый ключ из пары закрытого и открытого ключей. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameHashSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Возвращает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.  Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Удаляет указанный контейнер ключей. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameKeyGen](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Создает новую пару открытого и закрытого ключей для использования строгого имени.  Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Создает новую пару открытого и закрытого ключей с указанным размером ключа для строгого имени использования. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Импортирует пару открытого и закрытого ключей в контейнере.  Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Создает подпись со строгим именем для указанной сборки.   Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Создает подпись со строгим именем для указанной сборки, в зависимости от указанных флагов.    Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Возвращает размер подписи строгого имени. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени, которая будет проверена в соответствии с заданными флагами. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.  Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Проверяет допустимость сборки, который уже сопоставлен в памяти для связанного открытого ключа. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Создает маркер строгого имени из указанного файла сборки.  Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Функция StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Возвращает токен, представляющий открытый ключ. Устаревшими, начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Строгое именование структуры](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 Описываются неуправляемые структуры, использующего API со строгим именованием администрировать подписание сборки строгим именем...  
  
 [Структура PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Представляет открытый ключ из пары открытого и закрытого ключей в двоичном формате.  
  
## <a name="see-also"></a>См. также  
 [Iclrstrongname-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [Справочник по неуправляемым API](../../../../docs/framework/unmanaged-api/index.md)
