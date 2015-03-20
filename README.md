Java API for Google geocoder v3
======
1.Maven
------
#####Repository

Now artifact deployed to central repository

#####Artifact

    <dependencies>
      <dependency>
        <groupId>com.google.code.geocoder-java</groupId>
        <artifactId>geocoder-java</artifactId>
        <version>0.16</version>
      </dependency>
      <!-- ... -->
    </dependencies>

#####Direct Download

    http://repo1.maven.org/maven2/com/google/code/geocoder-java/geocoder-java/

#####Dependencies

######required
    com.google.code.gson:gson:2.2.4
    org.slf4j:slf4j-api:1.7.7

######optional
    commons-httpclient:commons-httpclient:3.1

2.Usage
------
#####Simple
    final Geocoder geocoder = new Geocoder();
    GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
    GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);

#####Google Map API Premier
    final Geocoder geocoder = new Geocoder("clientId","clientKey");
    GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
    GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);

#####via Proxy
    HttpClient httpClient = new HttpClient(new MultiThreadedHttpConnectionManager());
    httpClient.getHostConfiguration().setProxy("85.25.109.152", 3128);

    Geocoder geocoder = new AdvancedGeoCoder(httpClient);GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
    GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);

#####with timeout
    HttpClient httpClient = new HttpClient(new MultiThreadedHttpConnectionManager());
    httpClient.getParams().setParameter(HttpMethodParams.SO_TIMEOUT, 60 * 1000); //60s

    Geocoder geocoder = new AdvancedGeoCoder(httpClient);GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
    GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);

#####with GAE
    final Geocoder geocoder = new Geocoder();
    GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
    GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
    
3.Project Information
------
#####Code license
[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)

#####Owner
[panchmp](https://code.google.com/u/panchmp/)
