Copy from https://github.com/use-go/onvif

## 修改了以下内容(Modified the following)

### ./xsd/onvif/onvif.go
将 `struct` 中的 `\`xml:"onvif:XXXX"\`` 更改为 `\`xml:"XXXX"\``

### ./device/types.go

#### GetServicesResponse
将
```golang
type GetServicesResponse struct {
	Service Service
}
```
改为
```golang
type GetServicesResponse struct {
	Service []Service
}
```
#### GetServicesResponse
将
```
type DeviceServiceCapabilities struct {
	Network  NetworkCapabilities
	Security SecurityCapabilities
	System   SystemCapabilities
	Misc     MiscCapabilities
}
```
改为
```
type DeviceServiceCapabilities struct {
	Network  *NetworkCapabilities
	Security *SecurityCapabilities
	System   *SystemCapabilities
	Misc     *MiscCapabilities
}
```

## 安装(Installation)

To install the library,  use **go get**:

```go
go get github.com/VacantHusky/onvif
```