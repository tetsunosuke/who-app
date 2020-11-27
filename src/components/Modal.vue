<template>
<button type="button" class="btn btn-info" data-toggle="modal" data-target="#help">
help
</button>
<div class="modal" tabindex="-1" role="dialog" id="help">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">あそびかた</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <p>自己紹介ゲームです</p>
        <p>who? というゲームを勉強目的でオンライン実装しました</p>
        <p><a href="https://camp-fire.jp/projects/view/231360">コミュニティボードゲーム who? について</a>(CAMPFIREのサイトを開きます)</p>
        <hr/>
        <ol>
        <li>まずはどのプレイヤーがどの色になるかを決めてください</li>
        <li>テーマをボタンで選択してください（新テーマを自由に追加できます）</li>
        <li>全員がそのテーマに沿って自己紹介をします</li>
        <li>サイコロを振って出た色と数字の人の自己紹介テーマを当てます</li>
        </ol>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Modal'
}
</script>
