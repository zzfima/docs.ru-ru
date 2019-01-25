---
title: Объект My.WebServices (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: b3a486cb886e8f39081f30a2849e2d14573cf5e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676345"
---
# <a name="mywebservices-object"></a>Объект My.WebServices
Предоставляет свойства для создания и доступа к один экземпляр каждой веб-службы XML ссылается текущий проект.  
  
## <a name="remarks"></a>Примечания  
 Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект. Каждый экземпляр создается по запросу. Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`. Имя свойства совпадает с именем веб-службы, к которой обращается свойство. Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой. Сведения о добавлении в проект веб-служб, см. в разделе [доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 `My.WebServices` Объект предоставляет только веб-службы, связанный с текущим проектом. Она предоставляет доступ к веб-служб, объявленных в указанные библиотеки DLL. Для доступа к веб-службы, который предоставляет библиотеку DLL, необходимо использовать полное имя веб-службы, в виде *DllName*. *WebServiceName*. Дополнительные сведения см. в разделе [доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Объект и его свойства недоступны для веб-приложений.  
  
## <a name="properties"></a>Свойства  
 Каждое свойство `My.WebServices` объект предоставляет доступ к экземпляру веб-службы, который ссылается текущий проект. — Это имя свойства совпадает с именем веб-службы, который обращается к свойству, а тип свойства совпадает со значением типа веб службы.  
  
> [!NOTE]
>  Если имеется конфликт имен, имя свойства для доступа к веб-службы является *RootNamespace*_*пространства имен*\_*ServiceName*. Например, рассмотрим две веб-службы с именем `Service1`. Если один из этих служб находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, доступ к этой службе с помощью `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 При первом доступе к одной из `My.WebServices` свойств объекта, он создает новый экземпляр веб-службы и сохраняет его. Последующие обращения к этим свойствам возвращают этот экземпляр веб-службы.  
  
 Веб-службы можно освободить путем назначения `Nothing` свойства для этой веб-службы. Метод задания свойства назначает `Nothing` к сохраненному значению. Если назначить любое значение, отличное от `Nothing` свойству, метод задания значения создает исключение <xref:System.ArgumentException> исключение.  
  
 Вы можете протестировать свойство `My.WebServices` объект сохраняет экземпляр веб-службы с помощью `Is` или `IsNot` оператор. Эти операторы можно использовать для проверки, является ли значение свойства `Nothing`.  
  
> [!NOTE]
>  Как правило `Is` или `IsNot` оператор имеет считывается значение свойства для выполнения сравнения. Тем не менее если это свойство в настоящее время сохраняет `Nothing`, свойство создает новый экземпляр веб-службы, а затем возвращает этот экземпляр. Тем не менее, компилятор Visual Basic обрабатывает свойства `My.WebServices` специально, а также позволяет `Is` или `IsNot` оператор, чтобы проверить состояние свойства без изменения его значения.  
  
## <a name="example"></a>Пример  
 В этом примере вызывается `FahrenheitToCelsius` метод `TemperatureConverter` веб-службы XML и возвращает результат.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 Для работы этого примера проект должен ссылаться на веб-службы с именем `Converter`, и этой веб-службы должен предоставлять `ConvertTemperature` метод. Дополнительные сведения см. в разделе [доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Этот код не работает в проект веб-приложения.  
  
## <a name="requirements"></a>Требования  
  
### <a name="availability-by-project-type"></a>Доступность по типу проекта  
  
|Тип проекта|Доступно|  
|---|---|  
|Приложение Windows|**Да**|  
|Библиотека классов|**Да**|  
|Консольное приложение|**Да**|  
|Библиотека элементов управления Windows|**Да**|  
|Web Control Library|**Да**|  
|Служба Windows|**Да**|  
|Веб-сайт|Нет|  
  
## <a name="see-also"></a>См. также
- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
