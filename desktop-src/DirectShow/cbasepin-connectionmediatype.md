---
Description: The ConnectionMediaType method retrieves the media type for the current pin connection, if any. This method implements the IPin::ConnectionMediaType method.
ms.assetid: 57d100ba-4171-4caa-ab98-66a0a327a53b
title: CBasePin.ConnectionMediaType method
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# CBasePin.ConnectionMediaType method

The **ConnectionMediaType** method retrieves the media type for the current pin connection, if any. This method implements the [**IPin::ConnectionMediaType**](/windows/desktop/api/Strmif/nf-strmif-ipin-connectionmediatype) method.

## Syntax


```C++
HRESULT ConnectionMediaType(
   AM_MEDIA_TYPE *pmt
);
```



## Parameters

<dl> <dt>

*pmt* 
</dt> <dd>

Pointer to an [**AM\_MEDIA\_TYPE**](/windows/desktop/api/strmif/ns-strmif-_ammediatype) structure that receives the media type.

</dd> </dl>

## Return value

Returns an **HRESULT** value. Possible values include those in the following table.



| Return code                                                                                           | Description                           |
|-------------------------------------------------------------------------------------------------------|---------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>                  | Success.<br/>                   |
| <dl> <dt>**E\_POINTER**</dt> </dl>             | **NULL** pointer argument.<br/> |
| <dl> <dt>**VFW\_E\_NOT\_CONNECTED**</dt> </dl> | Pin is not connected.<br/>      |



 

## Remarks

If the pin is connected, this method copies the media type into the [**AM\_MEDIA\_TYPE**](/windows/desktop/api/strmif/ns-strmif-_ammediatype) structure specified by *pmt*. The caller must free the media type's format block. You can use the [**CoTaskMemFree**](https://msdn.microsoft.com/library/windows/desktop/ms680722) function, or the [**FreeMediaType**](freemediatype.md) helper function.

If the pin is not connected, this method zeroes the memory block specified by *pmt* and returns an error code.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Amfilter.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBasePin Class**](cbasepin.md)
</dt> </dl>

 

 



