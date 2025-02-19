<template>
    <v-container>
        <h2>ノートブック</h2>

        <div class="menuBox">
            <v-btn color="secondary" prepend-icon="mdi-plus">
                新規作成
                <v-dialog
                    v-model="newNoteDialog"
                    activator="parent"
                    width="80%">
                    <v-card>
                        <v-card-title>新規ノート</v-card-title>
                        <v-card-text>
                            <p>タイトル</p>
                            <v-text-field></v-text-field>
                            <p>内容</p>
                            <v-textarea></v-textarea>
                        </v-card-text>
                        <v-card-actions>
                            <v-btn color="primary">保存</v-btn>
                            <v-btn color="error" @click="newNoteDialog = false">キャンセル</v-btn>
                        </v-card-actions>
                    </v-card>
                </v-dialog>
            </v-btn>
        </div>

        <v-table density="compact">
            <thead>
                <tr>
                    <th>ID</th>
                    <th>登録日時</th>
                    <th class="tableTitle">タイトル</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>1</td>
                    <td>2025/01/01 12:00</td>
                    <td>タイトル1</td>
                </tr>
                <tr>
                    <td>2</td>
                    <td>2025/01/02 12:00</td>
                    <td>タイトル2</td>
                </tr>
                <tr>
                    <td>3</td>
                    <td>2025/01/03 12:00</td>
                    <td>タイトル3</td>
                </tr>
            </tbody>
        </v-table>
    </v-container>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const IsidVisible = ref(false);
const newNoteDialog = ref(false);
</script>

<style>
.menuBox {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 20px;
}

.tableTitle {
    width: 80%;
}
</style>