---
title: "Образец FindPrivateKey - WCF"
ms.date: 12/04/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 32e1a4a3de01371d67be8d19613b1f29c1ce3c29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="findprivatekey-sample"></a>Образец FindPrivateKey

Определение расположения и имени файла закрытого ключа, связанного с заданным сертификатом X.509, в хранилище сертификатов может представлять собой достаточно сложную задачу. Средство FindPrivateKey.exe упрощает этот процесс.

> [!IMPORTANT]
> FindPrivateKey - это образец, который необходимо скомпилировать перед началом использования. В разделе [построение проекта FindPrivateKey](#to-build-the-findprivatekey-project) разделе инструкции по созданию средство FindPrivateKey.

Сертификаты X.509 устанавливаются администратором или любым пользователем компьютера. Однако сертификат может обращаться служба, выполняющаяся с другой учетной записью. Например учетную запись СЕТЕВОЙ службы.

У такой учетной записи может не быть доступа к файлу закрытого ключа, поскольку изначально сертификат был установлен другой учетной записью. Средство FindPrivateKey позволяет определить расположение файла закрытого ключа заданного сертификата X.509. Если расположение файла закрытого ключа заданного сертификата X.509 известно, можно добавлять или удалять разрешения на доступ к этому файлу.

Образцы, которые используют сертификаты для безопасности с помощью средства FindPrivateKey в *Setup.bat* файла. Когда файл закрытого ключа будет найден, можно использовать другие средства, например *Cacls.exe* для установки соответствующих прав доступа в файле.

При запуске службы Windows Communication Foundation (WCF) учетной записи пользователя, например резидентно размещенного исполняемого файла, убедитесь, что учетная запись пользователя имеет доступ только для чтения к файлу. При запуске службы WCF в Internet Information Services (IIS) учетные записи по умолчанию, которые служба будет выполняться, NETWORK SERVICE в службах IIS 7 и более ранних версий, или удостоверение пула приложений IIS 7.5 и более поздними версиями. Дополнительные сведения см. в разделе [удостоверений пула приложений](/iis/manage/configuring-security/application-pool-identities).

## <a name="examples"></a>Примеры

При доступе к сертификата, для которого у процесса нет права на чтения, появится сообщение об исключении примерно следующим образом:

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

В этом случае с помощью средства FindPrivateKey найти файл закрытого ключа и затем задайте права доступа для процесса, в которой запущена служба. Например это можно сделать с помощью средства Cacls.exe, как показано в следующем примере:

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>Построение проекта FindPrivateKey

Чтобы загрузить проект, посетите [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

1. Откройте [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] и перейдите к *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* папки в каталоге, где установлен образец.

2. Дважды щелкните значок файла с расширением SLN, чтобы открыть файл в Visual Studio.

3. В **построения** последовательно выберите пункты **Перестроить решение**.

4. В результате построения решения будет создан файл FindPrivateKey.exe.

## <a name="conventionscommand-line-entries"></a>Соглашения-записи командной строки

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

Если параметры не указаны в командной строке, отображается этот текст справки.

## <a name="examples"></a>Примеры

Этот пример находит имя файла сертификата с именем субъекта «CN = localhost», в личном хранилище текущего пользователя.

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

Этот пример находит имя файла сертификата с именем субъекта «CN = localhost», в личное хранилище текущего пользователя и выводит полный путь к каталогу.

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

Этот пример находит имя файла сертификата с отпечатком "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" в хранилище "Личное" на локальном компьютере.

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
