---
title: Образец обнаружения службы с уникальным URI прослушивания
ms.date: 03/30/2017
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
ms.openlocfilehash: 7e1c5ae0cb1a44c72a27566035b4bc20acbf1614
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077048"
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a>Образец обнаружения службы с уникальным URI прослушивания
В этом образце показано обнаружение службы, свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> которой имеет значение <xref:System.ServiceModel.Description.ListenUriMode.Unique>. Если свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> имеет значение <xref:System.ServiceModel.Description.ListenUriMode.Unique>, то гарантируется уникальность ListenUri. Для этого задается уникальный порт либо к пути добавляется идентификатор GUID, чтобы сделать его уникальным.  
  
### <a name="features-on-the-service"></a>Возможности на стороне службы  
 Свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> устанавливается в значение <xref:System.ServiceModel.Description.ListenUriMode.Unique> для конечной точки TCP. Затем для службы разрешается обнаружение через конечную точку <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
### <a name="features-on-the-client"></a>Функции на стороне клиента  
 Этот клиент подключается к службе с использованием правильного `Via.Uri` или с помощью метода <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>. Затем возвращенный методом объект <xref:System.ServiceModel.Discovery.FindResponse> запрашивается, чтобы определить, содержит ли он допустимый <xref:System.ServiceModel.Endpoint.ListenUri%2A> и отличается ли этот URI от `Address.Uri`. Затем нужные сведения передаются в метод `InvokeCalculatorService`. В методе `InvokeCalculatorService` свойство <xref:System.ServiceModel.Endpoint.ListenUri%2A> передается вызывающим объектом, а затем в конечную точку клиента добавляется `ClientViaBehavior` с правильным `Via.Uri`.  
  
##### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл UniqueListenUriMode.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Запустите приложение службы, созданное в папке [основной каталог решения]\service\bin\debug.  
  
4.  Запустите клиентское приложение, созданное в папке [основной каталог решения]\Client\bin\debug.  
  
     Клиент определяет запущенную службу и записывает на консоль метаданные, опубликованные конечной точкой службы.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a>См. также
