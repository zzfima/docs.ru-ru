---
title: Ссылки на объекты
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: bc9c318fc0e05f384a00df7cd1436a138315d880
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714678"
---
# <a name="object-references"></a>Ссылки на объекты
В данном образце показано, как передать объекты по ссылкам между сервером и клиентом. В этом примере используются смоделированные *социальные сети*. Социальная сеть состоит из класса `Person`, содержащего список друзей, в котором каждый друг является экземпляром класса `Person` с собственным списком друзей. Таким образом создается граф объектов. Служба предоставляет операции для этих социальных сетей.  
  
 В этом образце служба размещается в службах IIS, а клиентом является консольное приложение (EXE).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="service"></a>Service  
 К классу `Person` применен атрибут<xref:System.Runtime.Serialization.DataContractAttribute>. Полю <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> присвоено значение `true`, объявляющее его ссылочным типом. Ко всем свойствам применяется атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
```csharp
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
  
 Операция `GetPeopleInNetwork` принимает параметр типа `Person` и возвращает всех людей в сети; то есть всех людей в списке `friends`, друзей друзей и так далее без повторений.  
  
```csharp
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 Операция `GetMutualFriends` принимает параметр типа `Person` и возвращает всех друзей в списке, которые также имеют этого человека в их списке `friends`.  
  
```csharp
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
  
 Операция `GetCommonFriends` принимает список типа `Person`. Предполагается, что в списке присутствует два объекта `Person`. Операция возвращает список объектов `Person`, находящихся в списках `friends` обоих объектов `Person`, в списке ввода.  
  
```csharp
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a>Клиент  
 Прокси клиента создается с помощью функции **Добавление ссылки на службу** в Visual Studio.  
  
 Создается социальная сеть, состоящая из пяти объектов `Person`. Клиент вызывает каждый из трех методов службы.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a>См. также:

- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- [Справочные сведения о взаимодействии объектов](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
