---
title: Объект My. WebService (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: c887f9b7c5a41c0aa02016354c46d5507b103d25
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918181"
---
# <a name="mywebservices-object"></a>Объект My.WebServices
Предоставляет свойства для создания и доступа к одному экземпляру каждой веб-службы XML, на которую ссылается текущий проект.  
  
## <a name="remarks"></a>Примечания  
 Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект. Каждый экземпляр создается по запросу. Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`. Имя свойства совпадает с именем веб-службы, к которой обращается свойство. Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой. Сведения о добавлении веб-служб в проект см. в разделе [доступ к веб-службам приложений](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 `My.WebServices` Объект предоставляет только веб-службы, связанные с текущим проектом. Он не предоставляет доступ к веб-службам, объявленным в упоминаемых в них библиотеках DLL. Для доступа к веб-службе, предоставляемой библиотекой DLL, необходимо использовать полное имя веб-службы в формате *dllname*. *WebServiceName*. Дополнительные сведения см. в разделе [доступ к веб-службам приложений](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Объект и его свойства недоступны для веб-приложений.  
  
## <a name="properties"></a>Свойства  
 Каждое свойство `My.WebServices` объекта предоставляет доступ к экземпляру веб-службы, на которую ссылается текущий проект. Имя свойства совпадает с именем веб-службы, к которой обращается свойство, а тип свойства совпадает с типом веб-службы.  
  
> [!NOTE]
> При конфликте имен имя свойства для доступа к веб-службе — *RootNamespace*_*Namespace*\_*ServiceName*. Например, рассмотрим две веб-службы с `Service1`именем. Если одна из этих служб находится в корневом пространстве `WindowsApplication1` имен и в пространстве `Namespace1`имен, доступ к этой службе будет осуществляться с помощью `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 При первом доступе к одному из `My.WebServices` свойств объекта он создает новый экземпляр веб-службы и сохраняет его. Последующие обращения к этому свойству возвращают этот экземпляр веб-службы.  
  
 Вы можете удалить веб-службу, назначив ей `Nothing` свойство для этой веб-службы. Метод задания свойства присваивает `Nothing` хранимому значению. Если присвоить значение, отличное `Nothing` от свойства, метод задания <xref:System.ArgumentException> выдаст исключение.  
  
 Можно проверить, сохраняет ли свойство `My.WebServices` объекта экземпляр веб-службы с `Is` помощью оператора или `IsNot` . С помощью этих операторов можно проверить, имеет `Nothing`ли свойство значение.  
  
> [!NOTE]
> Как правило, `Is` оператор `IsNot` или должен считывать значение свойства для выполнения сравнения. Однако если текущее свойство хранится `Nothing`, свойство создает новый экземпляр веб-службы, а затем возвращает этот экземпляр. Однако компилятор Visual Basic обрабатывает свойства `My.WebServices` объекта особым образом и `Is` позволяет оператору или `IsNot` проверить состояние свойства без изменения его значения.  
  
## <a name="example"></a>Пример  
 В этом примере вызывается `FahrenheitToCelsius` метод `TemperatureConverter` веб-службы XML и возвращается результат.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Чтобы этот пример работал, проект должен ссылаться на веб-службу с именем `Converter`, и эта веб-служба должна `ConvertTemperature` предоставлять метод. Дополнительные сведения см. в разделе [доступ к веб-службам приложений](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Этот код не работает в проекте веб-приложения.  
  
## <a name="requirements"></a>Требования  
  
### <a name="availability-by-project-type"></a>Доступность по типу проекта  
  
|Тип проекта|Доступно|  
|---|---|  
|Приложение Windows|**Да**|  
|Библиотека классов|**Да**|  
|Консольное приложение|**Да**|  
|Библиотека элементов управления Windows|**Да**|  
|Библиотека веб-элементов управления|**Да**|  
|Служба Windows|**Да**|  
|Веб-сайт|Нет|  
  
## <a name="see-also"></a>См. также

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
