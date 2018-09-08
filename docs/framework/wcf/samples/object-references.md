---
title: Ссылки на объекты
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: 1aa8b1c9d135186dba9e4da75f0c7cb9297d8e5c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185692"
---
# <a name="object-references"></a><span data-ttu-id="cc629-102">Ссылки на объекты</span><span class="sxs-lookup"><span data-stu-id="cc629-102">Object References</span></span>
<span data-ttu-id="cc629-103">В данном образце показано, как передать объекты по ссылкам между сервером и клиентом.</span><span class="sxs-lookup"><span data-stu-id="cc629-103">This sample demonstrates how to pass objects by references between server and client.</span></span> <span data-ttu-id="cc629-104">Данном образце используются смоделированные *социальных сетей*.</span><span class="sxs-lookup"><span data-stu-id="cc629-104">The sample uses simulated *social networks*.</span></span> <span data-ttu-id="cc629-105">Социальная сеть состоит из класса `Person`, содержащего список друзей, в котором каждый друг является экземпляром класса `Person` с собственным списком друзей.</span><span class="sxs-lookup"><span data-stu-id="cc629-105">A social network consists of a `Person` class that contains a list of friends in which each friend is an instance of the `Person` class, with its own list of friends.</span></span> <span data-ttu-id="cc629-106">Таким образом создается граф объектов.</span><span class="sxs-lookup"><span data-stu-id="cc629-106">This creates a graph of objects.</span></span> <span data-ttu-id="cc629-107">Служба предоставляет операции для этих социальных сетей.</span><span class="sxs-lookup"><span data-stu-id="cc629-107">The service exposes operations on these social networks.</span></span>  
  
 <span data-ttu-id="cc629-108">В этом образце служба размещается в службах IIS, а клиентом является консольное приложение (EXE).</span><span class="sxs-lookup"><span data-stu-id="cc629-108">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc629-109">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="cc629-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="cc629-110">Служба</span><span class="sxs-lookup"><span data-stu-id="cc629-110">Service</span></span>  
 <span data-ttu-id="cc629-111">К классу `Person` применен атрибут<xref:System.Runtime.Serialization.DataContractAttribute>. Полю <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> присвоено значение `true`, объявляющее его ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="cc629-111">The `Person` class has the <xref:System.Runtime.Serialization.DataContractAttribute> attribute applied, with the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> field set to `true` to declare it as a reference type.</span></span> <span data-ttu-id="cc629-112">Ко всем свойствам применяется атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cc629-112">All properties have the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute applied.</span></span>  
  
```  
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 <span data-ttu-id="cc629-113">Операция `GetPeopleInNetwork` принимает параметр типа `Person` и возвращает всех людей в сети; то есть всех людей в списке `friends`, друзей друзей и так далее без повторений.</span><span class="sxs-lookup"><span data-stu-id="cc629-113">The `GetPeopleInNetwork` operation takes a parameter of type `Person` and returns all the people in the network; that is, all the people in the `friends` list, the friend's friends, and so on, without duplicates.</span></span>  
  
```  
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 <span data-ttu-id="cc629-114">Операция `GetMutualFriends` принимает параметр типа `Person` и возвращает всех друзей в списке, которые также имеют этого человека в их списке `friends`.</span><span class="sxs-lookup"><span data-stu-id="cc629-114">The `GetMutualFriends` operation takes a parameter of type `Person` and returns all the friends in the list who also have this person in their `friends` list.</span></span>  
  
```  
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 <span data-ttu-id="cc629-115">Операция `GetCommonFriends` принимает список типа `Person`.</span><span class="sxs-lookup"><span data-stu-id="cc629-115">The `GetCommonFriends` operation takes a list of type `Person`.</span></span> <span data-ttu-id="cc629-116">Предполагается, что в списке присутствует два объекта `Person`.</span><span class="sxs-lookup"><span data-stu-id="cc629-116">The list is expected to have two `Person` objects in it.</span></span> <span data-ttu-id="cc629-117">Операция возвращает список объектов `Person`, находящихся в списках `friends` обоих объектов `Person`, в списке ввода.</span><span class="sxs-lookup"><span data-stu-id="cc629-117">The operation returns a list of `Person` objects that are in the `friends` lists of both `Person` objects in the input list.</span></span>  
  
```  
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a><span data-ttu-id="cc629-118">"Клиент";</span><span class="sxs-lookup"><span data-stu-id="cc629-118">Client</span></span>  
 <span data-ttu-id="cc629-119">Прокси клиента создается с помощью **Add Service Reference** функции Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cc629-119">The client proxy is created using the **Add Service Reference** feature of Visual Studio.</span></span>  
  
 <span data-ttu-id="cc629-120">Создается социальная сеть, состоящая из пяти объектов `Person`.</span><span class="sxs-lookup"><span data-stu-id="cc629-120">A social network that consists of five `Person` objects is created.</span></span> <span data-ttu-id="cc629-121">Клиент вызывает каждый из трех методов службы.</span><span class="sxs-lookup"><span data-stu-id="cc629-121">The client calls each of the three methods in the service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cc629-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cc629-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cc629-123">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cc629-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="cc629-124">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cc629-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="cc629-125">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cc629-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc629-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc629-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cc629-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cc629-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cc629-128">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="cc629-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cc629-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cc629-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a><span data-ttu-id="cc629-130">См. также</span><span class="sxs-lookup"><span data-stu-id="cc629-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 [<span data-ttu-id="cc629-131">Справочные сведения о взаимодействии объектов</span><span class="sxs-lookup"><span data-stu-id="cc629-131">Interoperable Object References</span></span>](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
