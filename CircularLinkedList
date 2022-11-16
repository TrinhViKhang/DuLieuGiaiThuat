class Node:
    def __init__(self, data): #Tạo node
        self.data = data 
        self.next = None


class CircularLinkedList: #Tạo CircularLinkedList
    def __init__(self):
        self.head = None 

    def prepend(self, data): #Hàm chuẩn bị trước 1 danh sách rỗng
        new_node = Node(data)
        cur = self.head 
        new_node.next = self.head

        if not self.head:
            new_node.next = new_node
        else:
            while cur.next != self.head:
                cur = cur.next
            cur.next = new_node
        self.head = new_node

    def add(self, data): #Hàm thêm giá trị
        if not self.head:
            self.head = Node(data)
            self.head.next = self.head
        else:
            new_node = Node(data)
            cur = self.head
            while cur.next != self.head:
                cur = cur.next
            cur.next = new_node
            new_node.next = self.head

    def print_list(self): #Hàm xuất ra màn hình
        cur = self.head 

        while cur:
            print(cur.data)
            cur = cur.next
            if cur == self.head:
                break

    def __len__(self):  #Đếm số để xóa vị trí Hoàng Tử
        cur = self.head
        count = 0
        while cur:
            count += 1
            cur = cur.next
            if cur == self.head:
                break
        return count

    def remove(self, key):
        if self.head.data == key:
            cur = self.head
            while cur.next != self.head:
                cur = cur.next
            cur.next = self.head.next
            self.head = self.head.next
        else:
            cur = self.head
            prev = None
            while cur.next != self.head:
                prev = cur 
                cur = cur.next
                if cur.data == key:
                    prev.next = cur.next
                    cur = cur.next

    def remove_node(self, node):
        if self.head == node:
            cur = self.head 
            while cur.next != self.head:
                cur = cur.next 
            cur.next = self.head.next 
            self.head = self.head.next
        else:
            cur = self.head 
            prev = None
            while cur.next != self.head:
                prev = cur 
                cur = cur.next 
                if cur == node:
                    prev.next = cur.next
                    cur = cur.next

    def delvitri(self, step): #Hàm xóa vị trí
        cur = self.head 

        while len(self) > 1:
            count = 1 
            while count != step:
                cur = cur.next 
                count += 1
            print("Đã xóa vị trí:" + str(cur.data))
            self.remove_node(cur)
            cur = cur.next


if __name__=="__main__":
    cllist = CircularLinkedList()
    #cllist.append(1)
    n = int(input("Nhập số lượng Hoàng Tử tham gia:")) #Nhập số lượng Hoàng Tử tham gia
    for i in range(1, n +1 ):
        x = int(input('Nhập vị trí Hoàng Tử thứ %i: '%i)) #Nhập vị trí từng Hoàng Tử
        cllist.add(x)

    r = int(input('Nhập vị trí bắt đầu đếm để xóa:')) #Nhập vị trí bắt đầu để xóa Hoàng Tử
    cllist.delvitri(r)
    print('Vị trí mà Hoàng Tử nên chọn là:') #Xuất ra vị trí cuối cùng/Hoàng Tử nên chọn
    cllist.print_list()
