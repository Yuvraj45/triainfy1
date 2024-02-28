# triainfy1
<p><code>
<b>ExeceptionalControllerAdvice------></b>
@RestControllerAdvice
public class ExeceptionalControllerAdvice{
@Autowired
private Environment environment;
@ExceptionHandler(Exception.class)
public responseEntity<*ErrorInfo*> generalExceptionalHandler(Exception ex){
@ExceptionHandler(trivaInfyException.class)
public responseEntity<*ErrorInfo*> trivainfyExceptionalHandler(trivaInfyException ex){
@ExceptionHandler({MethodArgumentNotValidException.class,ConstaintVoilationException.class})
public responseEntity<*ErrorInfo*> generalExceptionalHandler(Exception ex){
</code></p>
<p><code>
  <b> triainfyController.java--------></b>
@RequestMapping
@RestController
@Validated
public class TrivaInfyController{
@Aotowired
public TrivaInfyService trivaInfyService;
@GetMapping("hotels/{hotelNameSearchkey}")
list<*HotelDTO*> searchHotels(@pathvariable @valid String hotelNameSearchKey) throws
TrivaInfyException{
    List<*HotelDTO*> list=trivaInfyservice.searchHotels(hotelNameSearchkey);
    return list;
    }
  @GetMapping("vendors/{vendorNameSearchkey}")
list<*vendorDTO*> searchvendors(@pathvariable @valid String vendorNameSearchKey) throws
TrivaInfyException{
    List<*vendorDTO*> list=trivaInfyservice.searchVendors(vendorNameSearchkey);
    return list;
    }
  



  
</code></p>
