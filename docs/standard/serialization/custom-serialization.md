---
title: Пользовательская сериализация
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binary serialization, custom serialization
- custom serialization
- binary serialization, controlling
- OptionalFieldAttribute class, custom serialization
- ISerializable interface, custom serialization
- OnDeserializingAttribute class, custom serialization
- OnSerializedAttribute class, custom serialization
- serialization, custom serialization
- serialization, controlling
- OnDeserializedAttribute class, custom serialization
- OnSerializingAttribute class, custom serialization
ms.assetid: 12ed422d-5280-49b8-9b71-a2ed129c0384
ms.openlocfilehash: 60fdc0317975d94433401e3214953b77d0970f60
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741058"
---
# <a name="custom-serialization"></a>Пользовательская сериализация
Пользовательской сериализацией называется процесс управления сериализацией и десериализацией типа. Управление сериализацией позволяет обеспечить совместимость сериализации, в результате чего становится возможной сериализация и десериализация между различными версиями типа без нарушения основных функциональных возможностей типа. Например, в первой версии типа может быть только два поля. В следующей версии типа добавлено еще несколько полей. Во второй версии приложения должна быть предусмотрена возможность сериализации и десериализации обоих типов. В следующих разделах объясняется, как управлять сериализацией.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
> [!IMPORTANT]
> В версиях ранее .NET Framework 4.0 сериализация пользовательских данных в сборке с частичным доверием выполнялась методом GetObjectData. Начиная с версии 4.0, этот метод помечен атрибутом <xref:System.Security.SecurityCriticalAttribute>, который запрещает выполнение в сборках с частичным доверием. Чтобы решить эту проблему, реализуйте интерфейс <xref:System.Runtime.Serialization.ISafeSerializationData>.  
  
## <a name="running-custom-methods-during-and-after-serialization"></a>Использование пользовательских методов во время сериализации и после нее  
 Для исправления данных во время сериализации и после нее рекомендуется применять к методам следующие атрибуты (впервые представлено в платформе .NET Framework версии 2.0):  
  
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
 Эти атрибуты обеспечивают использование типа на любом или на всех четырех этапах процесса сериализации и десериализации. Атрибуты определяют методы типа, которые должны вызываться на каждом этапе. Доступ методов к потоку сериализации отсутствует, однако можно изменить объект перед сериализацией и после нее или перед десериализацией и после нее. Атрибуты можно применять на всех уровнях иерархии наследования типов, и каждый метод вызывается в иерархии от базового до самого дальнего в цепочке наследования. Этот механизм позволяет избежать усложненности и каких-либо проблем реализации интерфейса <xref:System.Runtime.Serialization.ISerializable>, передав процесс сериализации и десериализации самой дальней в цепочке наследования реализации. Кроме того, благодаря такому механизму модули форматирования могут игнорировать заполнение полей и извлечение данных из потока сериализации. Дополнительные сведения и примеры управления сериализацией и десериализацией см. по ссылкам выше.  
  
 Кроме того, при добавлении нового поля в существующий сериализуемый тип применяйте к полю атрибут <xref:System.Runtime.Serialization.OptionalFieldAttribute>. <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> игнорируют отсутствие поля, если обрабатывается поток без нового поля.  
  
## <a name="implementing-the-iserializable-interface"></a>Реализация интерфейса ISerializable  
 Еще одним способом управления сериализацией является реализация для объекта интерфейса <xref:System.Runtime.Serialization.ISerializable>. Однако следует помнить, что метод, описанный в предыдущем разделе, замещает этот метод управления сериализацией.  
  
 Кроме того, не следует использовать сериализацию по умолчанию для класса, который отмечен атрибутом [Serializable](xref:System.SerializableAttribute) и имеет декларативную или принудительную безопасность на уровне класса или конструкторов. В таких случаях в классах всегда следует реализовывать интерфейс <xref:System.Runtime.Serialization.ISerializable>.  
  
 Реализация <xref:System.Runtime.Serialization.ISerializable> включает реализацию метода `GetObjectData` и специального конструктора, который используется при десериализации объекта. В следующем образце кода показано, как реализовать <xref:System.Runtime.Serialization.ISerializable> в классе `MyObject` на основе информации предыдущего раздела.  
  
```csharp
[Serializable]
public class MyObject : ISerializable
{
    public int n1;
    public int n2;
    public String str;

    public MyObject()
    {
    }

    protected MyObject(SerializationInfo info, StreamingContext context)
    {
      n1 = info.GetInt32("i");
      n2 = info.GetInt32("j");
      str = info.GetString("k");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public virtual void GetObjectData(SerializationInfo info, StreamingContext context)
    {
        info.AddValue("i", n1);
        info.AddValue("j", n2);
        info.AddValue("k", str);
    }
}
```

```vb
<Serializable()>  _
Public Class MyObject
    Implements ISerializable
    Public n1 As Integer
    Public n2 As Integer
    Public str As String

    Public Sub New()
    End Sub

    Protected Sub New(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        n1 = info.GetInt32("i")
        n2 = info.GetInt32("j")
        str = info.GetString("k")
    End Sub 'New

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overridable Sub GetObjectData(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        info.AddValue("i", n1)
        info.AddValue("j", n2)
        info.AddValue("k", str)
    End Sub
End Class
```  
  
 Если во время сериализации вызывается **GetObjectData**, следует указать информацию <xref:System.Runtime.Serialization.SerializationInfo>, которая предоставляется вместе с вызовом метода. Добавьте переменные, которые будут сериализованы как пары имен и значений. В качестве имени можно ввести любой текст. Переменные-члены, добавляемые в <xref:System.Runtime.Serialization.SerializationInfo> могут быть любыми при условии, что сериализуется достаточное количество данных для восстановления объекта при десериализации. Производные классы должны вызывать метод **GetObjectData** для базового объекта, если в последнем реализован интерфейс <xref:System.Runtime.Serialization.ISerializable>.  
  
 Обратите внимание, что сериализация позволяет другому коду просматривать или изменять данные экземпляра объекта, не доступные в ином случае. Поэтому код, выполняющий сериализацию, требует разрешения [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) с установленным флагом <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>. При политике безопасности по умолчанию такое разрешение не предоставляется коду, загруженному из Интернета или интрасети, и дается только коду на локальном компьютере. Метод **GetObjectData** должен быть явно защищен посредством запроса либо [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) с установленным флагом <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>, либо иных разрешений, которые предназначены специально для защиты закрытых данных.  
  
 Если в закрытом поле хранятся конфиденциальные сведения, для их защиты следует запрашивать соответствующие разрешения для **GetObjectData**. Помните, что код, которому предоставлены разрешения [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) с установленным флагом **SerializationFormatter**, может просматривать и изменять данные, которые хранятся в закрытых полях. Злонамеренный вызывающий объект с предоставленными разрешениями [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) может просматривать такие данные, как местоположения скрытых каталогов или предоставленные разрешения, и использовать такую информацию для повышения уязвимости системы безопасности компьютера. Полный список устанавливаемых флагов разрешений безопасности представлен в перечислении [SecurityPermissionFlag Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).  
  
 Следует особо отметить, что при добавлении <xref:System.Runtime.Serialization.ISerializable> в класс следует реализовать и **GetObjectData**, и специальный конструктор. Компилятор выдает предупреждение, если **GetObjectData** отсутствует. Но поскольку невозможно принудительно реализовать конструктор, при его отсутствии предупреждение не выводится, и при попытке десериализовать класс без конструктора создается исключение.  
  
 В текущей разработке предусмотрена поддержка метода <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A>, чтобы избежать возможных проблем с безопасностью и управлением версиями. Например, метод `SetObjectData` должен быть открытым, если он определяется как часть интерфейса. По этой причине пользователям следует написать код, чтобы метод **SetObjectData** не вызывался несколько раз. Иначе вредоносное приложение, вызывающее метод **SetObjectData** для объекта в процессе выполнения операции, может стать причиной возникновения проблем.  
  
 Во время десериализации информация <xref:System.Runtime.Serialization.SerializationInfo> передается классу с помощью предусмотренного для этого конструктора. При десериализации объекта все ограничения видимости, применимые к конструктору, игнорируются, поэтому класс можно отметить как открытый, защищенный, внутренний или закрытый. Однако рекомендуется защищать конструктор, если только класс не запечатан. В этом случае конструктор следует отметить как закрытый. Кроме того, конструктор должен выполнять тщательную проверку входных данных. Чтобы избежать неправильного использования вредоносным кодом, конструктор должен производить такие же проверки безопасности и наличия необходимых разрешений при попытках получить экземпляр подобного класса с помощью другого конструктора. При несоблюдении этой рекомендации вредоносный код может предварительно сериализовать объект, получить контроль над [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) с установленным флагом <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> и десериализовать объект на клиентском компьютере, обойдя любую защиту, которая была реализована во время построения стандартного экземпляра с использованием открытого конструктора.  
  
 Чтобы восстановить состояние объекта, необходимо всего лишь запросить значения переменных из <xref:System.Runtime.Serialization.SerializationInfo> по именам, использованным во время сериализации. Если в базовом классе реализовано <xref:System.Runtime.Serialization.ISerializable>, следует вызвать базовый конструктор, чтобы базовый объект смог восстановить свои переменные.  
  
 При создании нового производного класса на основе класса с реализацией <xref:System.Runtime.Serialization.ISerializable> в производном классе должны быть реализованы как конструктор, так и метод **GetObjectData**, если имеются переменные, подлежащие сериализации. В следующем примере показано, как это можно сделать с помощью рассмотренного ранее класса `MyObject`.  
  
```csharp
[Serializable]
public class ObjectTwo : MyObject
{
    public int num;

    public ObjectTwo()
      : base()
    {
    }

    protected ObjectTwo(SerializationInfo si, StreamingContext context)
      : base(si, context)
    {
        num = si.GetInt32("num");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public override void GetObjectData(SerializationInfo si, StreamingContext context)
    {
        base.GetObjectData(si,context);
        si.AddValue("num", num);
    }
}
```

```vb
<Serializable()>  _
Public Class ObjectTwo
    Inherits MyObject
    Public num As Integer

    Public Sub New()

    End Sub

    Protected Sub New(ByVal si As SerializationInfo, _
    ByVal context As StreamingContext)
        MyBase.New(si, context)
        num = si.GetInt32("num")
    End Sub

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overrides Sub GetObjectData(ByVal si As SerializationInfo, ByVal context As StreamingContext)
        MyBase.GetObjectData(si, context)
        si.AddValue("num", num)
    End Sub
End Class
```  
  
 Не забудьте вызвать базовый класс в конструкторе десериализации. Если этого не сделать, конструктор для базового класса никогда не вызывается, и после десериализации объект не является полностью построенным.  
  
 Объекты воссоздаются изнутри, вызов методов во время десериализации может привести к нежелательным побочным эффектам, поскольку вызываемые объекты могут относиться к ссылкам на объекты, которые не были десериализованы на момент вызова. Если в десериализуемом классе реализовано <xref:System.Runtime.Serialization.IDeserializationCallback>, во время десериализации всего графа объекта автоматически вызывается метод <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A>. На этом этапе все дочерние объекты, на которые имеются ссылки, полностью восстановлены. Типичным примером класса, который сложно десериализовать без использования прослушивателя событий, служит хэш-таблица. Вызов пар "ключ-значение" во время десериализации не представляет сложности, однако добавление таких объектов обратно в хэш-таблицу может быть затруднительным, поскольку нет никаких гарантий, что производные на основе хэш-таблицы классы десериализованы. Поэтому на данном этапе не рекомендуется вызывать методы для хэш-таблицы.  
  
## <a name="see-also"></a>См. также:

- [Двоичная сериализация](binary-serialization.md)
- [Сериализация XML и SOAP](xml-and-soap-serialization.md)
- [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md)
