<script lang="ts">
   import { 
        Table, TableBody, TableBodyCell, TableBodyRow, TableHead, TableHeadCell, 
        Button, 
        Datepicker, } from 'flowbite-svelte';
</script>
  
  <style>
    :global(html, body) {
        margin: 0;
        padding: 0;
        height: 100vh; /* Ensure the body takes the full height of the viewport */
        overflow: hidden; /* Disable scrolling on the entire page */
    }

    .dashboard {
        display: grid;
        grid-template-areas:
            "summary calendar"
            "booking calendar";
        grid-template-columns: 2fr 2fr;
        grid-template-rows: auto 1fr;
        gap: 1rem;
        height: 100vh;
        padding: 1rem;
        justify-content: center;
        background-color: #DBDBDB;
    }
  
    .box {
        background-color: #ECEBEB;
        border-radius: 0.5rem;
        padding: 1rem;
    }

    .title {
        font-size: 1.5rem; 
        font-weight: bold; 
        color: #333;
        padding-bottom: 1rem; /* Adds space below the text */
        text-align: left;
  
    }


    /*Summary Section*/
    .summary {
        grid-area: summary;
        padding: 2rem;
    }

    .container {
        display: flex;
        gap: 1rem;
    }

    .card {
        display: flex;
        align-items: center;
        background-color: #FAFAFA;
        border-radius: 8px;
        overflow: hidden;
        width: 16rem; /* 256px */
        height: 5rem; /* 80px */
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        border: 1px solid #ddd;
    }

    .number-section {
        color: white;
        font-size: 3rem;
    
        display: flex;
        align-items: center;
        justify-content: center;
        width: 5rem; /* 80px */
        height: 100%;
    }

    .status-section {
        display: flex;
        flex-direction: column;
        gap: 0.25rem;
        padding: 0 1rem;
    }

    .icon {
        font-size: 1.5rem;
    }

    .status-text {
        color: #333;
        font-size: 1rem;
        font-weight: 500;
    }
    
    /*Booking Request Section*/
    .booking {
        grid-area: booking;
        padding: 2rem;
    }
  
    /*Calendar & Table Section*/
    .calendar {
        grid-area: calendar;
        padding: 2rem;
    }
    

    
  </style>
  
  <div class="dashboard">

    <div class="box summary">
        <div class="title">
            Summary
        </div>
        
        <div class="container">
            <div class="card">
                <!-- Number Section -->
                <div class="number-section" style="background-color: #DF6630;">
                  12
                </div>
                <!-- Icon and Status Section -->
                <div class="status-section">
                  <i class="fa-solid fa-house-circle-check icon" style="color: #DF6630;"></i>
                  <span class="status-text">Occupied</span>
                </div>
              </div>
            <div class="card">
                <!-- Number Section -->
                <div class="number-section" style="background-color: #C6B796;">
                  06
                </div>
                <!-- Icon and Status Section -->
                <div class="status-section">
                  <i class="fa-solid fa-house-circle-xmark icon" style="color: #C6B796;"></i>
                  <span class="status-text">Vacant</span>
                </div>
              </div>
            <div class="card">
                <!-- Number Section -->
                <div class="number-section" style="background-color: #AC1F16;">
                  30
                </div>
                <!-- Icon and Status Section -->
                <div class="status-section">
                    <i class="fa-solid fa-house-chimney-user icon" style="color: #AC1F16;"></i>
                  <span class="status-text">Tenants</span>
                </div>
              </div>
        </div>
        
    </div>
  
    

    <div class="box booking">
        <div class="title">
            Booking Requests
        </div>
        
          <Table>
            <TableHead>
              <TableHeadCell>NAME</TableHeadCell>
              <TableHeadCell>DATE</TableHeadCell>
              <TableHeadCell>UNIT</TableHeadCell>
              <TableHeadCell>ACTION</TableHeadCell>
            </TableHead>
            <TableBody tableBodyClass="divide-y">
              <TableBodyRow>
                <TableBodyCell>Aling Bebang</TableBodyCell>
                <TableBodyCell>December 02, 2024</TableBodyCell>
                <TableBodyCell>Unit 01</TableBodyCell>
                <TableBodyCell>
                    <Button color="green">Accept</Button>
                    <Button color="red">Decline</Button>
                </TableBodyCell>
              </TableBodyRow>
              <TableBodyRow>
                <TableBodyCell>Mories Carl</TableBodyCell>
                <TableBodyCell>November 23, 2024</TableBodyCell>
                <TableBodyCell>Unit 06</TableBodyCell>
                <TableBodyCell>
                    <Button color="green">Accept</Button>
                    <Button color="red">Decline</Button>
                </TableBodyCell>
              </TableBodyRow>
              <TableBodyRow>
                <TableBodyCell>Anne Chuny</TableBodyCell>
                <TableBodyCell>April 28, 2024</TableBodyCell>
                <TableBodyCell>Unit 19</TableBodyCell>
                <TableBodyCell>
                    <Button color="green">Accept</Button>
                    <Button color="red">Decline</Button>
                </TableBodyCell>
              </TableBodyRow>
            </TableBody>
          </Table>
    </div>

    <div class="box calendar">
        <div class="title">
            Rent Payments
        </div>
        
        
            <Datepicker inline />
            <div class="payment-table">
                <div class="mt-6">
                    <table class="w-full border border-gray-300 text-left">
                      <thead class="bg-gray-100">
                        <tr>
                          <th class="py-2 px-4 text-gray-600">Date</th>
                          <th class="py-2 px-4 text-gray-600">Details</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr class="border-b">
                          <td class="py-2 px-4">December 1, 2024</td>
                          <td class="py-2 px-4">Payment Due</td>
                        </tr>
                        <tr>
                          <td class="py-2 px-4">December 5, 2024</td>
                          <td class="py-2 px-4">Late Fee Charged</td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
            </div>
        
            
              

    </div>

  </div>
  