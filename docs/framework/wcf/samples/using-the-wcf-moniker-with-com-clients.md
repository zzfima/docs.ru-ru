---
title: Использование моникера WCF с клиентами COM
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: d4d812c59a504f365eb3ad63ddd45ba5a66296e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183234"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a><span data-ttu-id="1397c-102">Использование моникера WCF с клиентами COM</span><span class="sxs-lookup"><span data-stu-id="1397c-102">Using the WCF Moniker with COM Clients</span></span>
<span data-ttu-id="1397c-103">В этом примере показано, как использовать кличка службы Windows Communication Foundation (WCF) для интеграции web-сервисов в среды разработки на основе COM, такие как Microsoft Office Visual Basic for Applications (Office VBA) или Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="1397c-103">This sample demonstrates how to use the Windows Communication Foundation (WCF) service moniker to integrate Web services into COM-based development environments, such as Microsoft Office Visual Basic for Applications (Office VBA) or Visual Basic 6.0.</span></span> <span data-ttu-id="1397c-104">Этот образец содержит клиент сервера скриптов Windows (VBS), поддерживающую библиотеку клиента (DLL) и библиотеку службы (DLL), размещенные службами IIS.</span><span class="sxs-lookup"><span data-stu-id="1397c-104">This sample consists of a Windows Script Host client (.vbs), a supporting client library (.dll), and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="1397c-105">Служба представляет собой службу калькулятора, а клиент COM вызывает для службы математические операции (сложение, вычитание, умножение и деление).</span><span class="sxs-lookup"><span data-stu-id="1397c-105">The service is a calculator service and the COM client calls math operations—Add, Subtract, Multiply, and Divide—on the service.</span></span> <span data-ttu-id="1397c-106">Действия клиента отображаются в окнах сообщений.</span><span class="sxs-lookup"><span data-stu-id="1397c-106">Client activity is visible in the message box windows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1397c-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1397c-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1397c-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1397c-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1397c-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1397c-109">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1397c-110">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="1397c-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1397c-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1397c-111">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 <span data-ttu-id="1397c-112">Служба реализует определенный контракт `ICalculator`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1397c-112">The service implements an `ICalculator` contract defined as shown in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="1397c-113">В образце показаны три альтернативных подхода к использованию моникера.</span><span class="sxs-lookup"><span data-stu-id="1397c-113">The sample demonstrates the three alternative approaches for using the moniker:</span></span>  
  
- <span data-ttu-id="1397c-114">Типизированный контракт: контракт регистрируется как видимый для модели COM тип на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="1397c-114">Typed contract – The contract is registered as a COM visible type on the client computer.</span></span>  
  
- <span data-ttu-id="1397c-115">Контракт WSDL: контракт предоставляется в виде документа WSDL.</span><span class="sxs-lookup"><span data-stu-id="1397c-115">WSDL contract – The contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="1397c-116">Контракт обмена метаданными: контракт извлекается в среде выполнения из конечной точки обмена метаданными (MEX).</span><span class="sxs-lookup"><span data-stu-id="1397c-116">Metadata Exchange contract – The contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="typed-contract"></a><span data-ttu-id="1397c-117">Типизированный контракт</span><span class="sxs-lookup"><span data-stu-id="1397c-117">Typed Contract</span></span>  
 <span data-ttu-id="1397c-118">Чтобы использовать моникер с типизированным контрактом, в COM следует зарегистрировать типы с правильными атрибутами для контракта службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-118">To use the moniker with a typed contract use, appropriately attributed types for the service contract must be registered with COM.</span></span> <span data-ttu-id="1397c-119">Во-первых, клиент должен быть создан с помощью [инструмента ServiceModel Metadata Utility Tool (Svcutil.exe).](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)</span><span class="sxs-lookup"><span data-stu-id="1397c-119">First, a client must be generated by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="1397c-120">Чтобы создать типизированную учетную запись-посредник, выполните следующую команду из командной строки в каталоге клиента.</span><span class="sxs-lookup"><span data-stu-id="1397c-120">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 <span data-ttu-id="1397c-121">Этот класс необходимо включить в проект, а проект следует настроить на создание во время компиляции подписанной сборки, видимой для COM.</span><span class="sxs-lookup"><span data-stu-id="1397c-121">This class must be included in a project and the project should be configured to generate a COM-visible, signed assembly when compiled.</span></span> <span data-ttu-id="1397c-122">В файле AssemblyInfo.cs необходимо указать следующий атрибут:</span><span class="sxs-lookup"><span data-stu-id="1397c-122">The following attribute should be included in the AssemblyInfo.cs file.</span></span>  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 <span data-ttu-id="1397c-123">После создания проекта зарегистрируйте типы, видимые для модели COM, с помощью `regasm`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1397c-123">After building the project, register the COM-visible types by using `regasm` as shown in the following example.</span></span>  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 <span data-ttu-id="1397c-124">Создаваемую сборку следует добавить в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="1397c-124">The assembly that is created should be added to the Global Assembly Cache.</span></span> <span data-ttu-id="1397c-125">Хотя это не является строго обязательным, такая операция упростит процесс поиска сборки средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="1397c-125">Though not strictly required, this simplifies the process of the runtime locating the assembly.</span></span> <span data-ttu-id="1397c-126">Следующая команда добавляет сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="1397c-126">The following command adds the assembly to the Global Assembly Cache.</span></span>  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> <span data-ttu-id="1397c-127">Для моникера службы требуется только регистрация типа, он не использует прокси-сервер для связи со службой.</span><span class="sxs-lookup"><span data-stu-id="1397c-127">The service moniker requires only the type registration and does not use the proxy to communicate with the service.</span></span>  
  
 <span data-ttu-id="1397c-128">Приложение клиента ComCalcClient.vbs использует функцию `GetObject` для создания прокси-сервера для службы с помощью синтаксиса моникера службы для указания адреса, привязки и контракта службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-128">ComCalcClient.vbs client application uses the `GetObject` function to construct a proxy for the service, using the service moniker syntax to specify the address, binding, and contract for the service.</span></span>  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 <span data-ttu-id="1397c-129">Используемые моникером параметры определяют следующее.</span><span class="sxs-lookup"><span data-stu-id="1397c-129">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="1397c-130">Адрес конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-130">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="1397c-131">Привязка, которую клиент должен использовать для подключения к этой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="1397c-131">The binding that the client should use to connect with that endpoint.</span></span> <span data-ttu-id="1397c-132">В этом случае используется определенная системой привязка wsHttpBinding, хотя пользовательские привязки можно определить в файлах конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="1397c-132">In this case, the system-defined wsHttpBinding is used though custom bindings can be defined in client configuration files.</span></span> <span data-ttu-id="1397c-133">Для использования с сервером скрипт Windows пользовательская привязка определяется в файле Cscript.exe.config в том же каталоге, где находится файл Cscript.exe.</span><span class="sxs-lookup"><span data-stu-id="1397c-133">For use with the Windows Script Host, the custom binding is defined in a Cscript.exe.config file in the same directory as Cscript.exe.</span></span>  
  
- <span data-ttu-id="1397c-134">Тип контракта, поддерживаемый конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="1397c-134">The type of the contract that is supported at the endpoint.</span></span> <span data-ttu-id="1397c-135">Это тип, который был создан и зарегистрирован выше.</span><span class="sxs-lookup"><span data-stu-id="1397c-135">This is the type that was generated and registered above.</span></span> <span data-ttu-id="1397c-136">Поскольку скрипт Visual Basic не обеспечивает строго типизированную среду COM, для контракта следует указать идентификатор.</span><span class="sxs-lookup"><span data-stu-id="1397c-136">Because Visual Basic script does not provide a strongly-typed COM environment, an identifier for the contract must be specified.</span></span> <span data-ttu-id="1397c-137">Этот глобальный уникальный идентификатор является `interfaceID` из файла CalcProxy.tlb, который можно просмотреть средствами COM, такими как программа просмотра объектов OLE/COM (OleView.exe).</span><span class="sxs-lookup"><span data-stu-id="1397c-137">This GUID is the `interfaceID` from CalcProxy.tlb, which can be viewed by using COM tools such as the OLE/COM Object Viewer (OleView.exe).</span></span> <span data-ttu-id="1397c-138">Для таких строго типизированных сред, как Office VBA или Visual Basic 6.0, добавление явной ссылки на библиотеку типа и последующее объявление типа объекта прокси можно использовать вместо параметра контракта.</span><span class="sxs-lookup"><span data-stu-id="1397c-138">For strongly-typed environments such as Office VBA or Visual Basic 6.0, adding an explicit reference to the type library and then declaring the type of the proxy object can be used in place of the contract parameter.</span></span> <span data-ttu-id="1397c-139">Это также обеспечивает поддержку IntelliSense во время разработки клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="1397c-139">This also provides IntelliSense support during client application development.</span></span>  
  
 <span data-ttu-id="1397c-140">После создания экземпляра прокси-сервера с моникером службы клиентское приложение может вызывать методы для прокси, результатом чего станет вызов инфраструктурой моникера службы соответствующих операций службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-140">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 При запуске образца в окне сообщений сервера скриптов Windows отображается ответ операции. Это свидетельствует о том, что клиент COM совершает звонки COM с помощью набранного моникера для связи с службой WCF. <span data-ttu-id="1397c-143">Несмотря на использование COM в клиентском приложении, взаимодействие со службой состоит только из вызовов веб-службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-143">Despite the use of COM in the client application, the communication with the service consists only of Web service calls.</span></span>  
  
## <a name="wsdl-contract"></a><span data-ttu-id="1397c-144">Контракт WSDL</span><span class="sxs-lookup"><span data-stu-id="1397c-144">WSDL Contract</span></span>  
 <span data-ttu-id="1397c-145">Чтобы использовать моникер с контрактом WSDL, регистрация библиотеки клиентов не требуется, однако контракт WSDL службы должен быть извлечен из нештатного механизма (например, с помощью браузера) для получения службой доступа к конечной точке WSDL.</span><span class="sxs-lookup"><span data-stu-id="1397c-145">To use the moniker with a WSDL contract, no client library registration is required but the WSDL contract for the service must be retrieved through an out-of-band mechanism such as using a browser to access the WSDL endpoint for the service.</span></span> <span data-ttu-id="1397c-146">После этого моникер может связываться с контрактом во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1397c-146">The moniker can then access that contract at execution time.</span></span>  
  
 <span data-ttu-id="1397c-147">Приложение клиента ComCalcClient.vbs использует функцию `FileSystemObject` для доступа к локально сохраненному файлу WSDL, затем снова использует функцию `GetObject`, чтобы создать для службы прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="1397c-147">The ComCalcClient.vbs client application uses the `FileSystemObject` to access the locally saved WSDL file and then again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
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
  
 <span data-ttu-id="1397c-148">Используемые моникером параметры определяют следующее.</span><span class="sxs-lookup"><span data-stu-id="1397c-148">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="1397c-149">Адрес конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-149">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="1397c-150">Привязка, которую должен использовать клиент для подключения к этой конечной точке, и пространство имен, в котором определяется эта привязка.</span><span class="sxs-lookup"><span data-stu-id="1397c-150">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="1397c-151">В этом случае используется `wsHttpBinding_ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="1397c-151">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="1397c-152">Язык WSDL, определяющий контракт.</span><span class="sxs-lookup"><span data-stu-id="1397c-152">The WSDL that defines the contract.</span></span> <span data-ttu-id="1397c-153">В данном случае это строка, считанная из файла serviceWsdl.xml.</span><span class="sxs-lookup"><span data-stu-id="1397c-153">In this case this is the string that has been read from the serviceWsdl.xml file.</span></span>  
  
- <span data-ttu-id="1397c-154">Имя и пространство имен контракта.</span><span class="sxs-lookup"><span data-stu-id="1397c-154">The name and namespace of the contract.</span></span> <span data-ttu-id="1397c-155">Эта идентификация требуется, поскольку WSDL может содержать не один контракт.</span><span class="sxs-lookup"><span data-stu-id="1397c-155">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1397c-156">По умолчанию службы WCF генерируют отдельные файлы WSDL для каждого пространства имен, которые используются.</span><span class="sxs-lookup"><span data-stu-id="1397c-156">By default, WCF services generate separate WSDL files for each namespace that the use.</span></span> <span data-ttu-id="1397c-157">Они связаны с использованием конструктора импорта WSDL.</span><span class="sxs-lookup"><span data-stu-id="1397c-157">These are linked with the use of the WSDL import construct.</span></span> <span data-ttu-id="1397c-158">Поскольку моникер ожидает одного определения WSDL, в службе должно использоваться либо одно пространство имен (как показано в этом образце), либо требуется объединение отдельных файлов вручную.</span><span class="sxs-lookup"><span data-stu-id="1397c-158">Because the moniker expects a single WSDL definition, the service must either use a single namespace as demonstrated in this sample or the separate files must be manually merged.</span></span>  
  
 <span data-ttu-id="1397c-159">После создания экземпляра прокси-сервера с моникером службы клиентское приложение может вызывать методы для прокси, результатом чего станет вызов инфраструктурой моникера службы соответствующих операций службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-159">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 При запуске образца в окне сообщений сервера скриптов Windows отображается ответ операции. <span data-ttu-id="1397c-161">Это свидетельствует о том, что клиент COM совершает звонки COM с помощью моникера с контрактом WSDL для связи с службой WCF.</span><span class="sxs-lookup"><span data-stu-id="1397c-161">This demonstrates a COM client making COM calls using the moniker with a WSDL contract to communicate with a WCF service.</span></span>  
  
## <a name="metadata-exchange-contract"></a><span data-ttu-id="1397c-162">Контракт обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="1397c-162">Metadata Exchange Contract</span></span>  
 <span data-ttu-id="1397c-163">Чтобы использовать моникер с контрактом MEX, регистрация клиента не требуется, как и в случае с контрактом WSDL.</span><span class="sxs-lookup"><span data-stu-id="1397c-163">To use the moniker with a MEX contract, as with the WSDL contract, no client registration is required.</span></span> <span data-ttu-id="1397c-164">Контракт для службы извлекается во время выполнения путем внутреннего использования обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="1397c-164">The contract for the service is retrieved at execution time through the internal use of Metadata Exchange.</span></span>  
  
 <span data-ttu-id="1397c-165">Клиентское приложение ComCalcClient.vbs повторно использует функцию `GetObject` для создания прокси-сервера для службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-165">The ComCalcClient.vbs client application again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 <span data-ttu-id="1397c-166">Используемые моникером параметры определяют следующее.</span><span class="sxs-lookup"><span data-stu-id="1397c-166">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="1397c-167">Адрес конечной точки обмена метаданными службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-167">The address of the service metadata exchange endpoint.</span></span>  
  
- <span data-ttu-id="1397c-168">Адрес конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-168">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="1397c-169">Привязка, которую должен использовать клиент для подключения к этой конечной точке, и пространство имен, в котором определяется эта привязка.</span><span class="sxs-lookup"><span data-stu-id="1397c-169">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="1397c-170">В этом случае используется `wsHttpBinding_ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="1397c-170">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="1397c-171">Имя и пространство имен контракта.</span><span class="sxs-lookup"><span data-stu-id="1397c-171">The name and namespace of the contract.</span></span> <span data-ttu-id="1397c-172">Эта идентификация требуется, поскольку WSDL может содержать не один контракт.</span><span class="sxs-lookup"><span data-stu-id="1397c-172">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
 <span data-ttu-id="1397c-173">После создания экземпляра прокси-сервера с моникером службы клиентское приложение может вызывать методы для прокси, результатом чего станет вызов инфраструктурой моникера службы соответствующих операций службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-173">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 При запуске образца в окне сообщений сервера скриптов Windows отображается ответ операции. <span data-ttu-id="1397c-175">Это свидетельствует о том, что клиент COM совершает звонки COM с помощью моникера с контрактом MEX для связи с службой WCF.</span><span class="sxs-lookup"><span data-stu-id="1397c-175">This demonstrates a COM client making COM calls using the moniker with a MEX contract to communicate with a WCF service.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="1397c-176">Настройка и сборка образца</span><span class="sxs-lookup"><span data-stu-id="1397c-176">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="1397c-177">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="1397c-177">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1397c-178">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1397c-178">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="1397c-179">Из команды разработчика Prompt для Visual Studio откройте папку «клиент-бин» под папку для конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="1397c-179">From a Developer Command Prompt for Visual Studio, open the \client\bin folder, under the language-specific folder.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1397c-180">Если вы используете Windows Vista, Windows Server 2008, Windows 7 или Windows Server 2008 R2, убедитесь, что вы запустите запрос команды с привилегиями администратора.</span><span class="sxs-lookup"><span data-stu-id="1397c-180">If you are using Windows Vista, Windows Server 2008, Windows 7, or Windows Server 2008 R2, make sure that you run the command prompt with administrator privileges.</span></span>  
  
4. <span data-ttu-id="1397c-181">Введите `tlbexp.exe client.dll /out:CalcProxy.tlb` для экспорта dll в файл tlb.</span><span class="sxs-lookup"><span data-stu-id="1397c-181">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="1397c-182">Появится сообщение "Предупреждение программы экспорта библиотек типов", однако это не свидетельствует о наличии проблем, поскольку универсальный тип не требуется.</span><span class="sxs-lookup"><span data-stu-id="1397c-182">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
5. <span data-ttu-id="1397c-183">Введите `regasm.exe /tlb:CalcProxy.tlb client.dll` для регистрации типов с COM.</span><span class="sxs-lookup"><span data-stu-id="1397c-183">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="1397c-184">Появится сообщение "Предупреждение программы экспорта библиотек типов", однако это не свидетельствует о наличии проблем, поскольку универсальный тип не требуется.</span><span class="sxs-lookup"><span data-stu-id="1397c-184">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
6. <span data-ttu-id="1397c-185">Введите `gacutil.exe /i client.dll` для добавления сборки в кэш Глобальной ассамблеи.</span><span class="sxs-lookup"><span data-stu-id="1397c-185">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="1397c-186">Запуск образца на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="1397c-186">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="1397c-187">Проверьте, что вы можете получить доступ к службе `http://localhost/servicemodelsamples/service.svc`с помощью браузера, введя следующий адрес: .</span><span class="sxs-lookup"><span data-stu-id="1397c-187">Test that you can access the service using a browser by typing in the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="1397c-188">Должна отобразиться страница подтверждения.</span><span class="sxs-lookup"><span data-stu-id="1397c-188">A confirmation page should be displayed in response.</span></span>  
  
2. <span data-ttu-id="1397c-189">Запустите файл ComCalcClient.vbs из папки \client в языковой папке.</span><span class="sxs-lookup"><span data-stu-id="1397c-189">Run ComCalcClient.vbs from \client, from under the language-specific folder.</span></span> <span data-ttu-id="1397c-190">Действия клиента отображаются в окнах сообщений.</span><span class="sxs-lookup"><span data-stu-id="1397c-190">Client activity is displayed in message box windows.</span></span>  
  
3. <span data-ttu-id="1397c-191">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1397c-191">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="1397c-192">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="1397c-192">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="1397c-193">Создайте на компьютере службы виртуальный каталог с именем ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="1397c-193">On the service computer, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="1397c-194">Скрипт Setupvroot.bat, включенный в образец, можно использовать для создания каталога диска и виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="1397c-194">The Setupvroot.bat script included with the sample can be used to create the disk directory and virtual directory.</span></span>  
  
2. <span data-ttu-id="1397c-195">Скопируйте файлы служебной программы из каталога %SystemDrive%\Inetpub\wwwroot\servicemodelsamples в виртуальный каталог ServiceModelSamples на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-195">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service computer.</span></span> <span data-ttu-id="1397c-196">Не забудьте включить файлы в каталог \bin.</span><span class="sxs-lookup"><span data-stu-id="1397c-196">Be sure to include the files in the \bin directory.</span></span>  
  
3. <span data-ttu-id="1397c-197">Скопируйте на клиентский компьютер файл клиентского скрипта из папки \client в языковой папке.</span><span class="sxs-lookup"><span data-stu-id="1397c-197">Copy the client script file from the \client folder, under the language-specific folder, to the client computer.</span></span>  
  
4. <span data-ttu-id="1397c-198">В файле скрипта измените значение адреса определения конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="1397c-198">In the script file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="1397c-199">Замените любые ссылки на "localhost" в адресе полным именем домена.</span><span class="sxs-lookup"><span data-stu-id="1397c-199">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
5. <span data-ttu-id="1397c-200">Скопируйте файл языка WSDL на компьютер клиента.</span><span class="sxs-lookup"><span data-stu-id="1397c-200">Copy the WSDL file to the client computer.</span></span> <span data-ttu-id="1397c-201">В файле языка WSDL (serviceWsdl.xml) замените любые ссылки на "localhost" в адресе полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="1397c-201">In the WSDL file, serviceWsdl.xml, replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
6. <span data-ttu-id="1397c-202">Скопируйте в каталог на клиентском компьютере библиотеку Client.dll из папки \client\bin\ в языковой папке.</span><span class="sxs-lookup"><span data-stu-id="1397c-202">Copy the Client.dll library from the \client\bin folder, under the language-specific folder, to a directory on the client computer.</span></span>  
  
7. <span data-ttu-id="1397c-203">В командной строке перейдите в каталог назначения на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="1397c-203">From a command prompt, navigate to that destination directory on the client computer.</span></span> <span data-ttu-id="1397c-204">При использовании Windows Vista или Windows Server 2008, убедитесь, что запустите запрос команды в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="1397c-204">If using Windows Vista or Windows Server 2008, make sure to run the command prompt as Administrator.</span></span>  
  
8. <span data-ttu-id="1397c-205">Введите `tlbexp.exe client.dll /out:CalcProxy.tlb` для экспорта dll в файл tlb.</span><span class="sxs-lookup"><span data-stu-id="1397c-205">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="1397c-206">Появится сообщение "Предупреждение программы экспорта библиотек типов", однако это не свидетельствует о наличии проблем, поскольку универсальный тип не требуется.</span><span class="sxs-lookup"><span data-stu-id="1397c-206">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
9. <span data-ttu-id="1397c-207">Введите `regasm.exe /tlb:CalcProxy.tlb client.dll` для регистрации типов с COM.</span><span class="sxs-lookup"><span data-stu-id="1397c-207">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="1397c-208">Убедитесь, что путь был установлен `regasm.exe` в папке, содержащейся перед запуском команды.</span><span class="sxs-lookup"><span data-stu-id="1397c-208">Ensure that path has been set to the folder that contains `regasm.exe` before you run the command.</span></span>  
  
10. <span data-ttu-id="1397c-209">Введите `gacutil.exe /i client.dll` для добавления сборки в кэш Глобальной ассамблеи.</span><span class="sxs-lookup"><span data-stu-id="1397c-209">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="1397c-210">Убедитесь, что путь был установлен `gacutil.exe` в папке, содержащейся перед запуском команды.</span><span class="sxs-lookup"><span data-stu-id="1397c-210">Ensure that path has been set to the folder that contains `gacutil.exe` before you run the command.</span></span>  
  
11. <span data-ttu-id="1397c-211">Убедитесь, что доступ к службе с клиентского компьютера можно получить из браузера.</span><span class="sxs-lookup"><span data-stu-id="1397c-211">Test that you can access the service from the client computer using a browser.</span></span>  
  
12. <span data-ttu-id="1397c-212">На клиентском компьютере запустите ComCalcClient.vbs.</span><span class="sxs-lookup"><span data-stu-id="1397c-212">On the client computer, launch ComCalcClient.vbs.</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="1397c-213">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="1397c-213">To clean up after the sample</span></span>  
  
- <span data-ttu-id="1397c-214">В целях безопасности удалите определение виртуального каталога и разрешения, предоставленные на шагах установки, по завершении работы с образцами.</span><span class="sxs-lookup"><span data-stu-id="1397c-214">For security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  
