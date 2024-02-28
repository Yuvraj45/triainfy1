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
  @PostMapping("booking")
  String bookHotel(@RequestBody BookingDTO bookingDto) throws TrivaInfyException {
    String msg=trivaInfyService.bookHotel(bookingDto);
    return msg;
  }
  @PutMapping("booking/{bookingId}/{noOfRoomsNew}")
  String updateBooking(@PAthVariable @valid @Min(value=1,message="{booking.bookingid.invalid}")
  Integer bookingId,
    @PathVariable @Valid @Min(value=1,message="{booking.noofrooms.invalid}" )Integer noOfRoomsNew
      throws TrivaInfyException {
    String msg=trivaInfyService.updateBooking(bookingId, noOfRoomsNew);
    return msg;
  }
  @DeleteMapping("booking/{bookingId}")
  String cancelBooking(@PathVAriable @Valid @Min(value=1,message="{booking.bookingid.invalid}")
  String msg=trivaInfyService.cancelBooking(bookingId);
  return msg;
  }

 <b> //DTO//</b>
 private String hotelName;
 private String vendorNAme;
 @Min(value=1,message="{booking.noofrookms.invalid}"
 private int noOfRooms;

 <b> TrivaInfyServiceImpl.</b>
 @Override
 @Transactional
 public List<hotelDTO> searchHotels(String hotelNameSearchKey) throws
   List<*Hotel*> hotelListFromRepo = hotelRepository.
     findByHotelNameConteiningIgnoreCase(hotelNameSearchKey
  if(hotelListFromRepo.isEmpty()){
      throw nw TrivaInfyException(TrivaInfyConstants.
          TRIVAINFY_SEARCH_HOTEL_INVALID.TOsTRING());
      }
  
 
  



  
</code></p>
