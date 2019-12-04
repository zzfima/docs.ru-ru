---
title: Использование моникера WCF с клиентами COM
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: faaf8e80402ddaef85dcf8d7bfe9b1da202227c9
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715292"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a>Использование моникера WCF с клиентами COM
В этом примере демонстрируется использование моникера службы Windows Communication Foundation (WCF) для интеграции веб-служб в среды разработки на основе COM, такие как Microsoft Office Visual Basic для приложений (Office VBA) или Visual Basic 6,0. Этот образец содержит клиент сервера скриптов Windows (VBS), поддерживающую библиотеку клиента (DLL) и библиотеку службы (DLL), размещенные службами IIS. Служба представляет собой службу калькулятора, а клиент COM вызывает для службы математические операции (сложение, вычитание, умножение и деление). Действия клиента отображаются в окнах сообщений.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 Служба реализует определенный контракт `ICalculator`, как показано в следующем примере кода.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 В образце показаны три альтернативных подхода к использованию моникера.  
  
- Типизированный контракт: контракт регистрируется как видимый для модели COM тип на клиентском компьютере.  
  
- Контракт WSDL: контракт предоставляется в виде документа WSDL.  
  
- Контракт обмена метаданными: контракт извлекается в среде выполнения из конечной точки обмена метаданными (MEX).  
  
## <a name="typed-contract"></a>Типизированный контракт  
 Чтобы использовать моникер с типизированным контрактом, в COM следует зарегистрировать типы с правильными атрибутами для контракта службы. Сначала необходимо создать клиент с помощью [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Чтобы создать типизированную учетную запись-посредник, выполните следующую команду из командной строки в каталоге клиента.  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 Этот класс необходимо включить в проект, а проект следует настроить на создание во время компиляции подписанной сборки, видимой для COM. В файле AssemblyInfo.cs необходимо указать следующий атрибут:  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 После создания проекта зарегистрируйте типы, видимые для модели COM, с помощью `regasm`, как показано в следующем примере.  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 Создаваемую сборку следует добавить в глобальный кэш сборок. Хотя это не является строго обязательным, такая операция упростит процесс поиска сборки средой выполнения. Следующая команда добавляет сборку в глобальный кэш сборок.  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> Для моникера службы требуется только регистрация типа, он не использует прокси-сервер для связи со службой.  
  
 Приложение клиента ComCalcClient.vbs использует функцию `GetObject` для создания прокси-сервера для службы с помощью синтаксиса моникера службы для указания адреса, привязки и контракта службы.  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,   
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 Используемые моникером параметры определяют следующее.  
  
- Адрес конечной точки службы.  
  
- Привязка, которую клиент должен использовать для подключения к этой конечной точке. В этом случае используется определенная системой привязка wsHttpBinding, хотя пользовательские привязки можно определить в файлах конфигурации клиента. Для использования с сервером скрипт Windows пользовательская привязка определяется в файле Cscript.exe.config в том же каталоге, где находится файл Cscript.exe.  
  
- Тип контракта, поддерживаемый конечной точкой. Это тип, который был создан и зарегистрирован выше. Поскольку скрипт Visual Basic не обеспечивает строго типизированную среду COM, для контракта следует указать идентификатор. Этот глобальный уникальный идентификатор является `interfaceID` из файла CalcProxy.tlb, который можно просмотреть средствами COM, такими как программа просмотра объектов OLE/COM (OleView.exe). Для таких строго типизированных сред, как Office VBA или Visual Basic 6.0, добавление явной ссылки на библиотеку типа и последующее объявление типа объекта прокси можно использовать вместо параметра контракта. Это также обеспечивает поддержку IntelliSense во время разработки клиентского приложения.  
  
 После создания экземпляра прокси-сервера с моникером службы клиентское приложение может вызывать методы для прокси, результатом чего станет вызов инфраструктурой моникера службы соответствующих операций службы.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 При запуске образца в окне сообщений сервера скриптов Windows отображается ответ операции. Это демонстрирует COM-клиент, выполняющий вызовы COM с помощью типизированного моникера для взаимодействия со службой WCF. Несмотря на использование COM в клиентском приложении, взаимодействие со службой состоит только из вызовов веб-службы.  
  
## <a name="wsdl-contract"></a>Контракт WSDL  
 Чтобы использовать моникер с контрактом WSDL, регистрация библиотеки клиентов не требуется, однако контракт WSDL службы должен быть извлечен из нештатного механизма (например, с помощью браузера) для получения службой доступа к конечной точке WSDL. После этого моникер может связываться с контрактом во время выполнения.  
  
 Приложение клиента ComCalcClient.vbs использует функцию `FileSystemObject` для доступа к локально сохраненному файлу WSDL, затем снова использует функцию `GetObject`, чтобы создать для службы прокси-сервер.  
  
```vbscript  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 Используемые моникером параметры определяют следующее.  
  
- Адрес конечной точки службы.  
  
- Привязка, которую должен использовать клиент для подключения к этой конечной точке, и пространство имен, в котором определяется эта привязка. В этом случае используется `wsHttpBinding_ICalculator`.  
  
- Язык WSDL, определяющий контракт. В данном случае это строка, считанная из файла serviceWsdl.xml.  
  
- Имя и пространство имен контракта. Эта идентификация требуется, поскольку WSDL может содержать не один контракт.  
  
    > [!NOTE]
    > По умолчанию службы WCF создают отдельные WSDL-файлы для каждого пространства имен, которое используется. Они связаны с использованием конструктора импорта WSDL. Поскольку моникер ожидает одного определения WSDL, в службе должно использоваться либо одно пространство имен (как показано в этом образце), либо требуется объединение отдельных файлов вручную.  
  
 После создания экземпляра прокси-сервера с моникером службы клиентское приложение может вызывать методы для прокси, результатом чего станет вызов инфраструктурой моникера службы соответствующих операций службы.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 При запуске образца в окне сообщений сервера скриптов Windows отображается ответ операции. Это демонстрирует COM-клиент, выполняющий вызовы COM с использованием моникера с контрактом WSDL для взаимодействия со службой WCF.  
  
## <a name="metadata-exchange-contract"></a>Контракт обмена метаданными  
 Чтобы использовать моникер с контрактом MEX, регистрация клиента не требуется, как и в случае с контрактом WSDL. Контракт для службы извлекается во время выполнения путем внутреннего использования обмена метаданными.  
  
 Клиентское приложение ComCalcClient.vbs повторно использует функцию `GetObject` для создания прокси-сервера для службы.  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 Используемые моникером параметры определяют следующее.  
  
- Адрес конечной точки обмена метаданными службы.  
  
- Адрес конечной точки службы.  
  
- Привязка, которую должен использовать клиент для подключения к этой конечной точке, и пространство имен, в котором определяется эта привязка. В этом случае используется `wsHttpBinding_ICalculator`.  
  
- Имя и пространство имен контракта. Эта идентификация требуется, поскольку WSDL может содержать не один контракт.  
  
 После создания экземпляра прокси-сервера с моникером службы клиентское приложение может вызывать методы для прокси, результатом чего станет вызов инфраструктурой моникера службы соответствующих операций службы.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 При запуске образца в окне сообщений сервера скриптов Windows отображается ответ операции. Это демонстрирует COM-клиент, выполняющий вызовы COM с использованием моникера с контрактом MEX для взаимодействия со службой WCF.  
  
#### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. В Командная строка разработчика для Visual Studio откройте папку \client\bin\ в папке для конкретного языка.  
  
    > [!NOTE]
    > Если используется [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 или Windows Server 2008 R2, командную строку необходимо запустить с привилегиями администратора.  
  
4. Введите `tlbexp.exe client.dll /out:CalcProxy.tlb`, чтобы экспортировать библиотеку DLL в TLB-файл. Появится сообщение "Предупреждение программы экспорта библиотек типов", однако это не свидетельствует о наличии проблем, поскольку универсальный тип не требуется.  
  
5. Введите `regasm.exe /tlb:CalcProxy.tlb client.dll`, чтобы зарегистрировать типы в COM. Появится сообщение "Предупреждение программы экспорта библиотек типов", однако это не свидетельствует о наличии проблем, поскольку универсальный тип не требуется.  
  
6. Введите `gacutil.exe /i client.dll`, чтобы добавить сборку в глобальный кэш сборок.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере  
  
1. Проверьте, что доступ к службе можно получить с помощью браузера, введя следующий адрес: `http://localhost/servicemodelsamples/service.svc`. Должна отобразиться страница подтверждения.  
  
2. Запустите файл ComCalcClient.vbs из папки \client в языковой папке. Действия клиента отображаются в окнах сообщений.  
  
3. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1. Создайте на компьютере службы виртуальный каталог с именем ServiceModelSamples. Скрипт Setupvroot.bat, включенный в образец, можно использовать для создания каталога диска и виртуального каталога.  
  
2. Скопируйте файлы служебной программы из каталога %SystemDrive%\Inetpub\wwwroot\servicemodelsamples в виртуальный каталог ServiceModelSamples на компьютере службы. Не забудьте включить файлы в каталог \bin.  
  
3. Скопируйте на клиентский компьютер файл клиентского скрипта из папки \client в языковой папке.  
  
4. В файле скрипта измените значение адреса определения конечной точки, чтобы оно соответствовало новому адресу службы. Замените любые ссылки на "localhost" в адресе полным именем домена.  
  
5. Скопируйте файл языка WSDL на компьютер клиента. В файле языка WSDL (serviceWsdl.xml) замените любые ссылки на "localhost" в адресе полным доменным именем.  
  
6. Скопируйте в каталог на клиентском компьютере библиотеку Client.dll из папки \client\bin\ в языковой папке.  
  
7. В командной строке перейдите в каталог назначения на клиентском компьютере. При использовании [!INCLUDE[wv](../../../../includes/wv-md.md)] или [!INCLUDE[lserver](../../../../includes/lserver-md.md)] обязательно запускайте командную строку от имени администратора.  
  
8. Введите `tlbexp.exe client.dll /out:CalcProxy.tlb`, чтобы экспортировать библиотеку DLL в TLB-файл. Появится сообщение "Предупреждение программы экспорта библиотек типов", однако это не свидетельствует о наличии проблем, поскольку универсальный тип не требуется.  
  
9. Введите `regasm.exe /tlb:CalcProxy.tlb client.dll`, чтобы зарегистрировать типы в COM. Убедитесь, что путь был задан для папки, содержащей `regasm.exe` перед выполнением команды.  
  
10. Введите `gacutil.exe /i client.dll`, чтобы добавить сборку в глобальный кэш сборок. Убедитесь, что путь был задан для папки, содержащей `gacutil.exe` перед выполнением команды.  
  
11. Убедитесь, что доступ к службе с клиентского компьютера можно получить из браузера.  
  
12. На клиентском компьютере запустите ComCalcClient.vbs.  
  
#### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
- В целях безопасности удалите определение виртуального каталога и разрешения, предоставленные на шагах установки, по завершении работы с образцами.  
