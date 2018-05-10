---
title: Расширение размещения с использованием ServiceHostFactory
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: e553fe161ffc5b50850d916cf1cef6b38dd5c1a9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="extending-hosting-using-servicehostfactory"></a>Расширение размещения с использованием ServiceHostFactory
Стандартные <xref:System.ServiceModel.ServiceHost> API для размещения служб в Windows Communication Foundation (WCF) — это точка расширяемости в архитектуре WCF. Пользователи могут наследовать свои собственные хост-классы от класса <xref:System.ServiceModel.ServiceHost>, как правило, чтобы переопределить <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> для использования <xref:System.ServiceModel.Description.ServiceDescription> с целью принудительного добавления конечных точек по умолчанию или изменения поведений до открытия службы.  
  
 В резидентной среде нет необходимости создавать пользовательский класс <xref:System.ServiceModel.ServiceHost>, поскольку записывается код, создающий узел, а после его создания в нем вызывается метод <xref:System.ServiceModel.ICommunicationObject.Open>. В промежутке между этими двумя операциями можно выполнять любые действия. Можно, например, добавить новое поведение <xref:System.ServiceModel.Description.IServiceBehavior>.  
  
```  
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 Такой подход нельзя использовать повторно. Код, управляющий описанием, кодируется в программе узла (в данном случае функция Main()), поэтому эту логику трудно повторно использовать в другом контексте. Также существуют другие способы добавления поведения <xref:System.ServiceModel.Description.IServiceBehavior>, для которых не требуется принудительный код. Можно наследовать атрибут от атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute> и использовать его в типе реализации службы или можно сделать пользовательское поведение настраиваемым и составить его динамически с использованием конфигурации.  
  
 Однако для решения этой проблемы можно также использовать варианты этого примера с незначительными различиями. Один подход заключается в перемещении кода, добавляющего ServiceBehavior, из функции `Main()` в метод <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> пользовательского класса, унаследованного от класса <xref:System.ServiceModel.ServiceHost>:  
  
```  
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 Затем внутри функции `Main()` можно использовать следующее.  
  
```  
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 Сейчас пользовательская логика инкапсулирована в пустую абстракцию, которую можно легко использовать повторно во множестве различных исполняемых файлах узла.  
  
 Способ использования пользовательского класса <xref:System.ServiceModel.ServiceHost> в службах IIS или службе активации Windows (WAS) неочевиден. Эти среды отличаются от резидентной среды, поскольку среда размещения создает <xref:System.ServiceModel.ServiceHost> от имени приложения. Инфраструктура размещения IIS и WAS ничего не знает о пользовательском классе, унаследованном от класса <xref:System.ServiceModel.ServiceHost>.  
  
 Фабрика <xref:System.ServiceModel.Activation.ServiceHostFactory> разработана для решения проблемы получения доступа к пользовательскому классу <xref:System.ServiceModel.ServiceHost> из IIS или WAS. Поскольку пользовательский узел, унаследованный от класса <xref:System.ServiceModel.ServiceHost>, динамически настроен и потенциально принадлежит к различным типам, среда размещения никогда не создает его напрямую. Вместо этого WCF использует шаблон фабрики для предоставления уровня косвенного обращения между средой размещения и конкретным типом службы. Если не задано иное, используется реализация фабрики <xref:System.ServiceModel.Activation.ServiceHostFactory> по умолчанию, возвращающая экземпляр класса <xref:System.ServiceModel.ServiceHost>. Но можно также предоставить собственную фабрику, которая возвращает унаследованный узел, указывая имя типа CLR реализации фабрики в @ServiceHost директивы.  
  
 Замысел заключается в том, что в основных случаях реализация собственной фабрики должна иметь простое применение. Например, ниже представлена пользовательская фабрика <xref:System.ServiceModel.Activation.ServiceHostFactory>, возвращающая класс, унаследованный от класса <xref:System.ServiceModel.ServiceHost>:  
  
```  
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 Для использования этой фабрики вместо фабрики по умолчанию необходимо указать имя типа в @ServiceHost директива следующим образом:  
  
```  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Хотя нет технических ограничений на операции с классом <xref:System.ServiceModel.ServiceHost>, возвращаемым методом <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, рекомендуется сохранять реализации фабрики как можно более простыми. При наличии значительного объема пользовательской логики рекомендуется разместить эту логику на узле, а не в фабрике, чтобы увеличить возможность ее повторного использования.  
  
 Существует еще один уровень размещения API, о котором следует упомянуть здесь. WCF также имеет <xref:System.ServiceModel.ServiceHostBase> и <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, из которого <xref:System.ServiceModel.ServiceHost> и <xref:System.ServiceModel.Activation.ServiceHostFactory> соответственно является производным. Существуют более сложные сценарии, в которых необходимо выгружать большие части системы метаданных с помощью собственных настроенных созданий.
