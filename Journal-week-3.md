Journal - Week 3

Tutorial - Using the iOS MapKit

The steps below will allow you to create a map that will display points of interest.

1.  Choose a location within the Storyboard for your map and use the search feature to select "Map Kit View."
2.  Click and drage the "Map Kit View" to the appropriate place within the view and set the constraints.
3.  Create a Swift file that corresponds with the View in the Storyboard.
4.  At the very top of the file, import MapKit and CoreLocation.
5.  Within the class(at the very top of the file) create an @IBOutlet (@IBOutlet weak var name: MKMapView!) and replace "name" with a description of the map.  
6.  Use the split screen view to wire the Map to the @IBOulet.
7.  Create a function in the Swift file.  This is where you will set the map to display a pin.
8.  Create a constant and set it equal to the function CLGeocoder.  Example: let geocoder = CLGeocoder()
9.  Use, the geocodeAddressString property to submit a geocoding request to a specific string.  Example: func geocodeAddressString(addressString: String, completionHandler: CLGeocodeCompletionHandler).  
10.  Replace addressString with the location you want to search.
11.  Replace CLGeocodeCompletionHandler with the CLPlacemark property that allows Latitude and Longitude to be stored.  Example:  completionHandler: {(placemarks: [CLPlacemark]?, error: NSError?) -> Void in
12.  Create a line of code for the first item in the array.  Example: if let placemark = placemarks?[0]
13.  Create curly braces below the line above.  This is where you will provide the detail for your pin.
14.  Create a property for the MKPointAnnotation function.  Example: let annotation = MKPointAnnotation()
15.  Add the "coordinate" property to the property created above and set it equal to (placemark.location?coordinate)! .  Example: annotation.coordinate = (placemark.location?.coordinate)!
16.  Set the title of the pin with the "title" property.  Example: annotation.title = "title goes here"
17.  Add the annotation to the Map View.  Example: self."name you used for IBOutlet".addAnnotation(annotation).  Note that we are using the self property becuase we are inside of a closure.  Also note that we are passing our annotation property inside of the ()
18.  Create another property and set place it in an array.  Example: let annotations = [annotation]
19. Set the map to animate the annotations by using self."name you used for IBOutlet".showAnnotations(annotations, animated: true).  Note that the first placeholder in the () is telling the map what to dispay and the second placeholder is turning animation on or off with a Bool.  A false statement would display the new region immediately without animations.
20. Sit back and watch your map display all of your pins!
  
