---
title: Практическое руководство. Задание привязки службы в конфигурации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 911c13b2a24c1906fe3da787460209f12296c993
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928588"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a><span data-ttu-id="f5c0b-102">Практическое руководство. Задание привязки службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="f5c0b-102">How to: Specify a Service Binding in Configuration</span></span>
<span data-ttu-id="f5c0b-103">В этом примере контракт `ICalculator` определен для базовой службы калькулятора, служба реализуется в классе `CalculatorService`, а затем ее конечная точка настраивается в файле Web.config с указанием того, что служба использует класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-103">In this example, an `ICalculator` contract is defined for a basic calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is configured in the Web.config file, where it is specified that the service uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="f5c0b-104">Описание способов настройки этой службы с помощью кода вместо файла конфигурации, см. в разделе [как: Указание привязки службы в коде](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="f5c0b-104">For a description of how to configure this service using code instead of a configuration, see [How to: Specify a Service Binding in Code](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md).</span></span>  
  
 <span data-ttu-id="f5c0b-105">В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-105">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="f5c0b-106">Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-106">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="f5c0b-107">В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-107">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="f5c0b-108">Все перечисленные ниже этапы конфигурации можно выполнить с помощью программы [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f5c0b-108">All of the following configuration steps can be undertaken using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="f5c0b-109">Копию исходного кода в этом примере, см. в разделе [basicbinding обеспечением](../../../docs/framework/wcf/samples/basicbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f5c0b-109">For the source copy of this example, see [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md).</span></span>  
  
### <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a><span data-ttu-id="f5c0b-110">Указание привязки BasicHttpBinding, используемой для настройки службы</span><span class="sxs-lookup"><span data-stu-id="f5c0b-110">To specify the BasicHttpBinding to use to configure the service</span></span>  
  
1. <span data-ttu-id="f5c0b-111">Определите контракт службы для данного типа службы.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-111">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="f5c0b-112">Реализуйте контракт службы в классе службы.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-112">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    >  <span data-ttu-id="f5c0b-113">Информация об адресе или привязке не указывается внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-113">Address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="f5c0b-114">Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-114">Also, code does not have to be written to fetch that information from the configuration file.</span></span>  
  
3. <span data-ttu-id="f5c0b-115">Создайте файл Web.config для настройки конечной точки для `CalculatorService`, использующей <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-115">Create a Web.config file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  
            <endpoint   
            <!-- Leave the address blank to be populated by default -->  
            <!-- from the hosting environment,in this case IIS, so -->  
            <!-- the address will just be that of the IIS Virtual -->  
            <!-- Directory. -->  
                address=""   
            <!-- Specify the binding type -->  
                binding="wsHttpBinding"  
            <!-- Specify the binding configuration name for that -->  
            <!-- binding type. This is optional but useful if you -->  
            <!-- want to modify the properties of the binding. -->  
            <!-- The bindingConfiguration name Binding1 is defined -->  
            <!-- below in the bindings element. -->  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <!-- Binding property values can be modified here. -->  
              <!-- See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="f5c0b-116">Создайте файл Service.svc, содержащий следующую строку, и поместите его в виртуальный каталог IIS.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-116">Create a Service.svc file that contains the following line and place it in your Internet Information Services (IIS) virtual directory.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="f5c0b-117">Изменение значений по умолчанию для свойств привязки</span><span class="sxs-lookup"><span data-stu-id="f5c0b-117">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="f5c0b-118">Для изменения одного из значений свойств по умолчанию <xref:System.ServiceModel.WSHttpBinding>, создайте новое имя конфигурации привязки - `<binding name="Binding1">` , в [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) элемент и задать новые значения для атрибутов привязка в этом элементе привязки.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-118">To modify one of the default property values of the <xref:System.ServiceModel.WSHttpBinding>, create a new binding configuration name - `<binding name="Binding1">` - within the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element and set the new values for the attributes of the binding in this binding element.</span></span> <span data-ttu-id="f5c0b-119">Например, чтобы изменить значения по умолчанию для времени ожидания при открытии и закрытии с 1 минуты на 2 минуты, добавьте следующие строки в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-119">For example, to change the default open and close timeout values of 1 minute to 2 minutes, add the following to the configuration file.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5c0b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f5c0b-120">See also</span></span>

- [<span data-ttu-id="f5c0b-121">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f5c0b-121">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f5c0b-122">Указание адреса конечной точки</span><span class="sxs-lookup"><span data-stu-id="f5c0b-122">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)
