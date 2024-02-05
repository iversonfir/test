import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class OrdersServiceTest {

    @Test
    public void givenOrderDetails_whenCreateOrder_thenOrderIsCreatedSuccessfully() {
        // Given
        OrdersService ordersService = new OrdersService();
        List<OrderItem> orderItems = new ArrayList<>();
        orderItems.add(new OrderItem(1, 101, 5, 100.0));

        // When
        Order newOrder = ordersService.createOrder(1, 500.0, orderItems);

        // Then
        assertNotNull(newOrder);
        assertEquals(1, newOrder.getId());
        assertEquals(500.0, newOrder.getTotalAmount());
        assertFalse(newOrder.getOrderItems().isEmpty());
    }
}
    