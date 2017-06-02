---
title: "Образец обнаружения службы с уникальным URI прослушивания | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Образец обнаружения службы с уникальным URI прослушивания
В этом образце показано обнаружение службы, свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> которой имеет значение <xref:System.ServiceModel.Description.ListenUriMode>.Если свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> имеет значение <xref:System.ServiceModel.Description.ListenUriMode>, то гарантируется уникальность ListenUri. Для этого задается уникальный порт либо к пути добавляется идентификатор GUID, чтобы сделать его уникальным.  
  
### Функции на стороне службы  
 Свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> устанавливается в значение <xref:System.ServiceModel.Description.ListenUriMode> для конечной точки TCP.Затем для службы разрешается обнаружение через конечную точку <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
### Функции на стороне клиента  
 Этот клиент подключается к службе с использованием правильного `Via.Uri` или с помощью метода <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>.Затем возвращенный методом объект <xref:System.ServiceModel.Discovery.FindResponse> запрашивается, чтобы определить, содержит ли он допустимый <xref:System.ServiceModel.Endpoint.ListenUri%2A> и отличается ли этот URI от `Address.Uri`.Затем нужные сведения передаются в метод `InvokeCalculatorService`.В методе `InvokeCalculatorService` свойство <xref:System.ServiceModel.Endpoint.ListenUri%2A> передается вызывающим объектом, а затем в конечную точку клиента добавляется `ClientViaBehavior` с правильным `Via.Uri`.  
  
##### Использование этого образца  
  
1.  Откройте файл UniqueListenUriMode.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Запустите приложение службы, созданное в папке \[основной каталог решения\]\\service\\bin\\debug.  
  
4.  Запустите клиентское приложение, созданное в папке \[основной каталог решения\]\\Client\\bin\\debug.  
  
     Клиент определяет запущенную службу и записывает на консоль метаданные, опубликованные конечной точкой службы.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## См. также