---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1ff00bead6130601070ac94686ee9622a6fe218
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="findprivatekey"></a>FindPrivateKey
Определение расположения и имени файла закрытого ключа, связанного с заданным сертификатом X.509, в хранилище сертификатов может представлять собой достаточно сложную задачу. Средство FindPrivateKey.exe упрощает этот процесс.  
  
> [!IMPORTANT]
>  FindPrivateKey - это образец, который необходимо скомпилировать перед началом использования. В разделе «Создание проекта FindPrivateKey» ниже инструкции о том, как построить инструмент FindPrivateKey.  
  
 Сертификаты X.509 устанавливаются администратором или любым пользователем компьютера. Однако к сертификату может обращаться служба, выполняющаяся от имени другой учетной записи (например, ASPNET в [!INCLUDE[wxp](../../../../includes/wxp-md.md)] или NETWORK SERVICE в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).  
  
 У такой учетной записи может не быть доступа к файлу закрытого ключа, поскольку изначально сертификат был установлен другой учетной записью. Средство FindPrivateKey позволяет определить расположение файла закрытого ключа заданного сертификата X.509. Если расположение файла закрытого ключа заданного сертификата X.509 известно, можно добавлять или удалять разрешения на доступ к этому файлу.  
  
 В примерах, безопасность которых обеспечивается с помощью сертификатов, средство FindPrivateKey запускается через файл Setup.bat. Когда файл закрытого ключа будет найден, можно с помощью других средств (например, Cacls.exe) установить для него соответствующие права доступа.  
  
 При выполнении службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], например резидентно размещенного исполняемого файла, от имени учетной записи пользователя необходимо проверить, что у пользователя есть доступ только для чтения к этому файлу. При выполнении службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в службах IIS по умолчанию служба выполняется от имени учетной записи ASPNET в [!INCLUDE[wxp](../../../../includes/wxp-md.md)] или NETWORK SERVICE в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], у которых по умолчанию нет доступа к файлу закрытого ключа.  
  
## <a name="examples"></a>Примеры  
 При обращении к сертификатам из процесса, у которого нет права на чтения этих сертификатов, появляется сообщение об исключении примерно следующего вида.  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 Если это происходит, необходимо с помощью средства FindPrivateKey найти файл закрытого ключа и предоставить доступ к нему для процесса, в котором выполняется служба. Например, это можно сделать с помощью средства Cacls.exe, как показано ниже.  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a>Построение проекта FindPrivateKey  
  
1.  Откройте [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] и перейдите к языковому подкаталогу в каталоге, где установлен пример.  
  
2.  Дважды щелкните значок файла с расширением SLN, чтобы открыть файл в Visual Studio.  
  
3.  В **построения** последовательно выберите пункты **Перестроить решение**. Файлы построения клиентской программы сохраняются в папке client\bin, а файлы построения служебной программы - в папке service\bin.  
  
4.  В результате построения решения будет создан файл FindPrivateKey.exe.  
  
## <a name="conventionscommand-line-entries"></a>Соглашения - записи командной строки  
 «[*параметр*]» представляет набор необязательных параметров.  
  
 «{*параметр*}» представляет набор обязательных параметров.  
  
 «*параметр1* &#124; *параметр2*«представляет выбор между наборами параметров.  
  
 «\<*значение*>» представляет значение параметра ввода.  
  
## <a name="usage"></a>Использование  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 Где:  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 Если в командной строке не указать ни один параметр, появится этот справочный текст.  
  
## <a name="examples"></a>Примеры  
 Этот пример находит имя файла сертификата с именем субъекта "CN=localhost" в хранилище "Личное" текущего пользователя. FindPrivateKey My CurrentUser -n "CN=localhost".  
  
 Этот пример находит имя файла сертификата с именем субъекта "CN=localhost" в хранилище "Личное" текущего пользователя и выводит полный путь к каталогу.  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 Этот пример находит имя файла сертификата с отпечатком "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" в хранилище "Личное" на локальном компьютере.  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a>См. также
