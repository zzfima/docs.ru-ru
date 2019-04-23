---
title: Использование DataContractSerializer и Data Contract Resolver для обеспечения функциональности NetDataContractSerializer
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 0378f8d6e21f44eb1f39e9ebf51ef0dfaf8d8e8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295150"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="7314c-102">Использование DataContractSerializer и Data Contract Resolver для обеспечения функциональности NetDataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="7314c-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="7314c-103">В образце описывается, как использование <xref:System.Runtime.Serialization.DataContractSerializer> с соответствующим <xref:System.Runtime.Serialization.DataContractResolver> обеспечивает функциональность, идентичную <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7314c-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="7314c-104">В следующем образце показано, как создать соответствующий <xref:System.Runtime.Serialization.DataContractResolver> и как добавить его к <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7314c-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

## <a name="sample-details"></a><span data-ttu-id="7314c-105">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="7314c-105">Sample details</span></span>
 <span data-ttu-id="7314c-106">Существует одно важное отличие <xref:System.Runtime.Serialization.NetDataContractSerializer> от <xref:System.Runtime.Serialization.DataContractSerializer>: <xref:System.Runtime.Serialization.NetDataContractSerializer> включает информацию о типе CLR в сериализованный XML, а <xref:System.Runtime.Serialization.DataContractSerializer> этого не делает.</span><span class="sxs-lookup"><span data-stu-id="7314c-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="7314c-107">Таким образом <xref:System.Runtime.Serialization.NetDataContractSerializer> может использоваться только при использовании одних и тех же типов CLR на концах сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="7314c-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="7314c-108">Однако рекомендуется использовать <xref:System.Runtime.Serialization.DataContractSerializer>, поскольку он обладает более высоким уровнем производительности, чем <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7314c-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="7314c-109">Можно изменить данные, сериализуемые в <xref:System.Runtime.Serialization.DataContractSerializer> при добавлении к нему <xref:System.Runtime.Serialization.DataContractResolver>.</span><span class="sxs-lookup"><span data-stu-id="7314c-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>

 <span data-ttu-id="7314c-110">Этот образец состоит из двух проектов.</span><span class="sxs-lookup"><span data-stu-id="7314c-110">This sample consists of two projects.</span></span> <span data-ttu-id="7314c-111">В первом проекте используется <xref:System.Runtime.Serialization.NetDataContractSerializer> для сериализации этого объекта.</span><span class="sxs-lookup"><span data-stu-id="7314c-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="7314c-112">Во втором проекте используется <xref:System.Runtime.Serialization.DataContractSerializer> с <xref:System.Runtime.Serialization.DataContractResolver> для обеспечения функциональности, идентичной первому проекту.</span><span class="sxs-lookup"><span data-stu-id="7314c-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>

 <span data-ttu-id="7314c-113">В следующем примере кода показана реализация пользовательского <xref:System.Runtime.Serialization.DataContractResolver> с именем `MyDataContractResolver`, добавленного к <xref:System.Runtime.Serialization.DataContractSerializer> в проекте DCSwithDCR.</span><span class="sxs-lookup"><span data-stu-id="7314c-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        if (type == null)
        {
            type = Type.GetType(typeName + ", " + typeNamespace);
        }
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="7314c-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="7314c-114">To use this sample</span></span>

1. <span data-ttu-id="7314c-115">Откройте файл решения DCRSample.sln в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="7314c-115">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="7314c-116">Щелкните правой кнопкой мыши файл решения и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="7314c-116">Right-click the solution file and choose **Properties**.</span></span>

3. <span data-ttu-id="7314c-117">В **страницы свойств решения** диалогового окна в разделе **общие свойства**, **запускаемым проектом**выберите **несколько запускаемых проектов:**.</span><span class="sxs-lookup"><span data-stu-id="7314c-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>

4. <span data-ttu-id="7314c-118">Рядом с полем **DCSwithDCR** проекта, выберите **запустить** из **действие** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7314c-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>

5. <span data-ttu-id="7314c-119">Рядом с полем **NetDCS** проекта, выберите **запустить** из **действие** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7314c-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>

6. <span data-ttu-id="7314c-120">Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="7314c-120">Click **OK** to close the dialog.</span></span>

7. <span data-ttu-id="7314c-121">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="7314c-121">To build the solution, press CTRL+SHIFT+B.</span></span>

8. <span data-ttu-id="7314c-122">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="7314c-122">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="7314c-123">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7314c-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7314c-124">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7314c-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7314c-125">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="7314c-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7314c-126">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7314c-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
