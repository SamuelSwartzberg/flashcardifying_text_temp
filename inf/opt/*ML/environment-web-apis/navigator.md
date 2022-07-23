# navigator

Instances of Navigator represent the identity and state of the user agent (the client).

## Geolocation API

the Geolocation API is used for location hadnling in the browser.
you get an object of Geolocation from navigator.geolocation
inteface Geolocation {
  getCurrentPosition(success: function, error?: function, options?: PositionOptions): void;
  watchPosition(success: function, error?: function, options?: PositionOptions): Id;
  clearWatch(Id): void;
}
interface GeolocationPosition {
  coords: GeolocationCoordiantes;
  timestamp: DOMTimeStamp;
}