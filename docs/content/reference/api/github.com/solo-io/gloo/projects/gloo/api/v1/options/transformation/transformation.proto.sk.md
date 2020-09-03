
---
title: "transformation.proto"
weight: 5
---

<!-- Code generated by solo-kit. DO NOT EDIT. -->


### Package: `transformation.options.gloo.solo.io` 
#### Types:


- [ResponseMatch](#responsematch)
- [RequestMatch](#requestmatch)
- [Transformations](#transformations)
- [RequestResponseTransformations](#requestresponsetransformations)
- [TransformationStages](#transformationstages)
  



##### Source File: [github.com/solo-io/gloo/projects/gloo/api/v1/options/transformation/transformation.proto](https://github.com/solo-io/gloo/blob/master/projects/gloo/api/v1/options/transformation/transformation.proto)





---
### ResponseMatch



```yaml
"matchers": []matchers.core.gloo.solo.io.HeaderMatcher
"responseCodeDetails": string
"responseTransformation": .envoy.api.v2.filter.http.Transformation

```

| Field | Type | Description | Default |
| ----- | ---- | ----------- |----------- | 
| `matchers` | [[]matchers.core.gloo.solo.io.HeaderMatcher](../../../core/matchers/matchers.proto.sk/#headermatcher) | Response headers to match on. |  |
| `responseCodeDetails` | `string` | Response code detail to match on. To see the response code details for your usecase, you can use the envoy access log %RESPONSE_CODE_DETAILS% formatter to log it. |  |
| `responseTransformation` | [.envoy.api.v2.filter.http.Transformation](../../../../external/envoy/extensions/transformation/transformation.proto.sk/#transformation) | Transformation to apply on the response. |  |




---
### RequestMatch



```yaml
"matcher": .matchers.core.gloo.solo.io.Matcher
"clearRouteCache": bool
"requestTransformation": .envoy.api.v2.filter.http.Transformation
"responseTransformation": .envoy.api.v2.filter.http.Transformation

```

| Field | Type | Description | Default |
| ----- | ---- | ----------- |----------- | 
| `matcher` | [.matchers.core.gloo.solo.io.Matcher](../../../core/matchers/matchers.proto.sk/#matcher) | Matches on the request properties. |  |
| `clearRouteCache` | `bool` | Should we clear the route cache if a transformation was matched. |  |
| `requestTransformation` | [.envoy.api.v2.filter.http.Transformation](../../../../external/envoy/extensions/transformation/transformation.proto.sk/#transformation) | Transformation to apply on the request. |  |
| `responseTransformation` | [.envoy.api.v2.filter.http.Transformation](../../../../external/envoy/extensions/transformation/transformation.proto.sk/#transformation) | Transformation to apply on the response. |  |




---
### Transformations



```yaml
"requestTransformation": .envoy.api.v2.filter.http.Transformation
"clearRouteCache": bool
"responseTransformation": .envoy.api.v2.filter.http.Transformation

```

| Field | Type | Description | Default |
| ----- | ---- | ----------- |----------- | 
| `requestTransformation` | [.envoy.api.v2.filter.http.Transformation](../../../../external/envoy/extensions/transformation/transformation.proto.sk/#transformation) | Apply a transformation to requests. |  |
| `clearRouteCache` | `bool` | Clear the route cache if the request transformation was applied. |  |
| `responseTransformation` | [.envoy.api.v2.filter.http.Transformation](../../../../external/envoy/extensions/transformation/transformation.proto.sk/#transformation) | Apply a transformation to responses. |  |




---
### RequestResponseTransformations



```yaml
"requestTransforms": []transformation.options.gloo.solo.io.RequestMatch
"responseTransforms": []transformation.options.gloo.solo.io.ResponseMatch

```

| Field | Type | Description | Default |
| ----- | ---- | ----------- |----------- | 
| `requestTransforms` | [[]transformation.options.gloo.solo.io.RequestMatch](../transformation.proto.sk/#requestmatch) | Transformations to apply on the request. The first request that matches will apply. |  |
| `responseTransforms` | [[]transformation.options.gloo.solo.io.ResponseMatch](../transformation.proto.sk/#responsematch) | Transformations to apply on the response. This field is only consulted if there is no response transformation in the matched `request_transforms`. i.e. Only one response transformation will be executed. The first response transformation that matches will apply. |  |




---
### TransformationStages



```yaml
"early": .transformation.options.gloo.solo.io.RequestResponseTransformations
"regular": .transformation.options.gloo.solo.io.RequestResponseTransformations

```

| Field | Type | Description | Default |
| ----- | ---- | ----------- |----------- | 
| `early` | [.transformation.options.gloo.solo.io.RequestResponseTransformations](../transformation.proto.sk/#requestresponsetransformations) | Early transformations happen before most other options (Like Auth and Rate Limit). |  |
| `regular` | [.transformation.options.gloo.solo.io.RequestResponseTransformations](../transformation.proto.sk/#requestresponsetransformations) | Regular transformations happen after Auth and Rate limit decisions has been made. |  |





<!-- Start of HubSpot Embed Code -->
<script type="text/javascript" id="hs-script-loader" async defer src="//js.hs-scripts.com/5130874.js"></script>
<!-- End of HubSpot Embed Code -->