---
title: Строгое именование (справочник по управляемым API)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
ms.openlocfilehash: 7d18513450111d58b5d26fd834addd465cfc4267
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140634"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Строгое именование (справочник по управляемым API)
API строгого именования позволяет клиенту администрировать подписание сборок строгим именем.  
  
 При подписи сборки строгим именем в файл, содержащий манифест сборки, добавляется зашифрованный открытый ключ. Подпись строгим именем гарантирует уникальность имени, предотвращает подмену имени и после разрешения ссылки предоставляет уникальный идентификатор вызывающему объекту. Однако со строгим именем не связано никакого уровня доверия.  
  
## <a name="in-this-section"></a>Содержание  
  
> [!NOTE]
> Все эти функции являются нерекомендуемыми начиная с .NET Framework 4. Рекомендуемые альтернативы см. в интерфейсе [ICLRStrongName](../hosting/iclrstrongname-interface.md).  
  
 [Функция GetHashFromAssemblyFile](gethashfromassemblyfile-function.md)  
 Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromAssemblyFileW](gethashfromassemblyfilew-function.md)  
 Получает хэш файла сборки, указанного строкой Юникода, с помощью указанного хэш-алгоритма. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromBlob](gethashfromblob-function.md)  
 Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromFile](gethashfromfile-function.md)  
 Создает хэш содержимого указанного файла.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromFileW](gethashfromfilew-function.md)  
 Создает хэш содержимого файла, указанного строкой Юникода. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция GetHashFromHandle](gethashfromhandle-function.md)  
 Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameCompareAssemblies](strongnamecompareassemblies-function.md)  
 Определяет, отличаются ли две сборки только подписями строгого имени. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameErrorInfo](strongnameerrorinfo-function.md)  
 Получает код последней ошибки, вызванной одной из функций строгого имени.  
  
 [Функция StrongNameFreeBuffer](strongnamefreebuffer-function.md)  
 Освобождает память, выделенную предыдущим вызовом функции строгого имени, такой как [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) или [StrongNameSignatureGeneration ](strongnamesignaturegeneration-function.md).   Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameGetBlob](strongnamegetblob-function.md)  
 Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameGetBlobFromImage](strongnamegetblobfromimage-function.md)  
 Получает двоичное представление образа сборки по указанному адресу памяти. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameGetPublicKey](strongnamegetpublickey-function.md)  
 Получает открытый ключ из пары закрытого и открытого ключей. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameHashSize](strongnamehashsize-function.md)  
 Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyDelete](strongnamekeydelete-function.md)  
 Удаляет указанный контейнер ключей. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyGen](strongnamekeygen-function.md)  
 Создает пару открытого и закрытого ключей для использования строгого имени.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyGenEx](strongnamekeygenex-function.md)  
 Создает пару открытого и закрытого ключей с заданным размером для использования строгого имени. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameKeyInstall](strongnamekeyinstall-function.md)  
 Импортирует пару открытого и закрытого ключей в контейнер.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)  
 Создает подпись строгого имени для указанной сборки.   Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureGenerationEx](strongnamesignaturegenerationex-function.md)  
 Создает подпись строгого имени для указанной сборки в зависимости от указанных флагов.    Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureSize](strongnamesignaturesize-function.md)  
 Возвращает размер подписи строгого имени. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureVerification](strongnamesignatureverification-function.md)  
 Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureVerificationEx](strongnamesignatureverificationex-function.md)  
 Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameSignatureVerificationFromImage](strongnamesignatureverificationfromimage-function.md)  
 Проверяет допустимость сборки, которая уже была сопоставлена с памятью, для связанного открытого ключа. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameTokenFromAssembly](strongnametokenfromassembly-function.md)  
 Создает маркер строгого имени из указанного файла сборки.  Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameTokenFromAssemblyEx](strongnametokenfromassemblyex-function.md)  
 Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Функция StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md)  
 Получает маркер, представляющий открытый ключ. Является нерекомендуемым начиная с версии .NET Framework 4.  
  
 [Структура PublicKeyBlob](publickeyblob-structure.md)  
 Представляет открытый ключ из пары открытого и закрытого ключей в двоичном формате.  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
- [Справочник по неуправляемым API](../index.md)
